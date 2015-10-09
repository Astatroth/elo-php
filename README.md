Elo PHP
=======

From [Wikipedia](https://en.wikipedia.org/wiki/Elo_rating_system):

The Elo rating system is a method for calculating the relative skill levels of players in competitor-versus-competitor games such as chess. It is named after its creator Arpad Elo, a Hungarian-born American physics professor.

Usage
-----

```php
<?php

require_once __DIR__ . '/src/Elo.php';

$elo = new Elo;

$player_a->rating = 1200;
$player_b->rating = 1430;

// 0 for a lose, 1 for a win
$player_a->score = 0;
$player_b->score = 1;

list(
	$player_a->new_rating, 
	$player_b->new_rating
) = $elo->new_rating(
	$player_a->rating, $player_b->rating, 
	$player_a->score, $player_b->score
);
```