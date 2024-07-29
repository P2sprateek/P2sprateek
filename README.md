```
import random

class Player:
    def __init__(self, name):
        self.name = name
        self.health = 100

    def attack(self, other):
        damage = random.randint(10, 20)
        other.health -= damage
        print(f"{self.name} attacks {other.name} for {damage} damage.")

    def is_alive(self):
        return self.health > 0

def game():
    player1 = Player("Player 1")
    player2 = Player("Player 2")

    while player1.is_alive() and player2.is_alive():
        print(f"\n{player1.name}'s health: {player1.health}")
        print(f"{player2.name}'s health: {player2.health}\n")

        player1.attack(player2)
        if player2.is_alive():
            player2.attack(player1)

    if player1.is_alive():
        print(f"{player1.name} wins!")
    else:
        print(f"{player2.name} wins!")

game()
```
