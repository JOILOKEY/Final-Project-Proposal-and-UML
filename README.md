**Final-Project-Proposal-and-UML** 

Final Project Proposal
Name: Joi
Course: CS121_4
Project Title: Go Fish Card Game

Project Summary
Title:
Go Fish: A Classic Card Game

Description:
This project is a console-based Java implementation of the classic Go Fish card game. Two players (one human, one computer) take turns asking each other for specific card ranks. If the opponent has any cards of the requested rank, they hand them over; otherwise, the player must "Go Fish" and draw from the deck. The goal is to form books (sets of four cards of the same rank). The game continues until all books have been collected, and the player with the most books wins. 

**Intended Users**:
Students learning Java and OOP

Casual users interested in card games

Anyone wanting to play a simple card game via the command line

**Problem Solved**:
Provides a fun, interactive way to learn basic game loops and state management

Helps students understand user input, loops, collections, and randomization in Java

Illustrates how to implement turn-based logic and basic computer-controlled behavior


Your hand: [5♣, 5♦, K♠, 2♣, A♦]
Your books: 0 | Computer's books: 1
Ask for a rank: 5

Computer has 5♦! You get another turn.
Your hand: [5♣, 5♦, 5♥, K♠, 2♣, A♦]
Ask for a rank: 5

Computer says "Go Fish!"
You drew: 5♠ — Book completed!
You now have 1 book of 5s!

[continues...]

**Data Design**
Core Classes:
Card

Fields: String rank, String suit

Methods: toString()

Deck

Fields: ArrayList<Card> cards

Methods: shuffle(), draw(), isEmpty()

Player (Superclass)

Fields: List<Card> hand, List<String> books

Methods: askForRank(), receiveCards(), checkForBooks()

HumanPlayer extends Player

Reads rank from user input

ComputerPlayer extends Player

Randomly picks a rank from its hand

GoFishGame

Fields: Deck, HumanPlayer, ComputerPlayer, currentTurn

Methods: playTurn(), checkWin(), startGame() 

**UI Design**
Command-Line Interface:

Prompts user to ask for a rank

Shows current hand and number of books

Displays messages like "Go Fish!" or “You got it!” 

Algorithm & Game Logic
Game Start:

Deck is created and shuffled

Each player is dealt 7 cards

Player Turn:

Ask opponent for a rank

If opponent has any, they give all of that rank

If not, draw a card from the deck

If a book (4 of same rank) is made, add it to player’s books

Turn Change:

Player gets another turn if they succeed

Switch turns otherwise

End Game:

Game ends when all books are made (13 total) or deck and hands are empty

Winner is the one with more books

