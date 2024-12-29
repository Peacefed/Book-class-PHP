<?php
ini_set('display_errors', 1);
require_once 'Book.php';

use Library\Book;

$book1 = new Book("Introduction to PHP", "SD Marlz", 5000); 
$book2 = new Book("Mastering Laravel", "Code Forge", 10000);
$book3 = new Book("OOP Concepts in Depth", "Tech Guru", 7000);

echo $book1->getDetails() . PHP_EOL . '<br>'. '<br>'; 
echo $book2->getDetails() . PHP_EOL . '<br>'. '<br>';
echo $book3->getDetails() . PHP_EOL . '<br>'. '<br>';

$book1->updatePrice(5500);
echo "After price update: <br> " . $book1->getDetails() . PHP_EOL . '<br>'. '<br>';

$budget = 8000; echo  '<br>'. '<br>';
echo $book3->isAffordable($budget) ? "You can afford '{$book3->getDetails()}'" : "You cannot afford '{$book3->getDetails()}'";
