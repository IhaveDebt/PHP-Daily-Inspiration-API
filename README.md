<?php
header("Content-Type: application/json");

class InspirationAPI {
    private $quotes = [
        "Push yourself, because no one else is going to do it for you.",
        "Success doesn’t come to you, you go to it.",
        "Great things never come from comfort zones.",
        "Dream it. Wish it. Do it.",
        "Don’t stop when you’re tired. Stop when you’re done.",
        "Doubt kills more dreams than failure ever will.",
        "Discipline is the bridge between goals and accomplishment.",
        "Your only limit is your mind.",
        "Do something today that your future self will thank you for."
    ];

    public function getQuote() {
        $index = array_rand($this->quotes);
        return [
            "quote" => $this->quotes[$index],
            "timestamp" => date("Y-m-d H:i:s")
        ];
    }
}

$api = new InspirationAPI();
echo json_encode($api->getQuote(), JSON_PRETTY_PRINT);
