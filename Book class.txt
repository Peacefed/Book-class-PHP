<?php


namespace Library;

class Book
{
    private $title;
    private $author;
    private $price;

    public function __construct($title, $author, $price)
    {
        $this->title = $title;
        $this->author = $author;
        $this->price = $price;
    }

    public function getDetails()
    {
        return "Title: {$this->title}, Author: {$this->author}, Price: ₦{$this->price}";
    }

    public function updatePrice($newPrice)
    {
        $this->price = $newPrice;
    }

    public function isAffordable($budget)
    {
        return $budget >= $this->price;
    }
}
