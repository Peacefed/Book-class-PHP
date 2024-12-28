<?php

class Book {
    private string $title;
    private string $author;
    private int $publicationYear;
    private float $price;

    public function __construct(string $title, string $author, int $publicationYear, float $price) {
        $this->title = $title;
        $this->author = $author;
        $this->publicationYear = $publicationYear;
        $this->price = $price;
    }

    public function getBookDetails(): string {
        return sprintf(
            "Title: %s\nAuthor: %s\nPublication Year: %d\nPrice: $%.2f",
            $this->title,
            $this->author,
            $this->publicationYear,
            $this->price
        );
    }

    public function updatePrice(float $newPrice): void {
        if ($newPrice > 0) {
            $this->price = $newPrice;
        } else {
            echo "Error: Price must be positive.\n";
        }
    }

    public function calculateDiscount(float $discountPercentage): float {
        if ($discountPercentage < 0 || $discountPercentage > 100) {
            echo "Error: Discount percentage must be between 0 and 100.\n";
            return $this->price;
        }
        return $this->price * (1 - $discountPercentage / 100);
    }

    public function getTitle(): string {
        return $this->title;
    }

    public function getAuthor(): string {
        return $this->author;
    }

    public function getPublicationYear(): int {
        return $this->publicationYear;
    }
}

// Create instances (objects) of the Book class
$book1 = new Book("To Die for Love", "Peace Nwabueze", 2024, 15.99);
$book2 = new Book("2023", "Peace Chinedu", 2004, 12.99);

// Interact with the Book objects
echo $book1->getBookDetails() . "\n\n";
echo $book2->getBookDetails() . "\n\n";

// Update the price of book1
$book1->updatePrice(17.99);
echo $book1->getBookDetails() . "\n\n";

// Calculate the discounted price for book2
$discountedPrice = $book2->calculateDiscount(20);
echo sprintf("Discounted price of '%s': $%.2f\n", $book2->getTitle(), $discountedPrice);

?>
