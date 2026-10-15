# Battleship

Battleship game for the terminal, written in Java. The player manually places their fleet and plays against a predefined enemy fleet. The interface uses ASCII output and ANSI colors.

## Requirements

- Java 8 or later
- Maven

## Build and run

From the project root:

```bash
mvn clean package
java -jar target/battleship-octubre-*-jar-with-dependencies.jar
```

During startup, enter each ship's coordinates when prompted. Then enter one coordinate per turn, using a column letter and a row number, for example `A3`.

To run the tests:

```bash
mvn test
```

## Fleet

Each fleet contains:

| Ship | Size |
| --- | ---: |
| Aircraft Carrier | 5 |
| Battleship | 4 |
| Submarine | 3 |
| Destroyer | 3 |
| Patrol Boat | 2 |

The console indicates a board with columns from `A` to `H` and rows from `1` to `8`.

## Current status

This is an initial implementation: the enemy fleet is defined in the code, the computer's shots are random, and the game continues without automatically detecting a win or loss. Ship placement validation is tested separately, but is not yet enforced during console input.

## Project structure

- `src/main/java/org/scrum/psd/battleship/ascii`: application entry point and terminal interface.
- `src/main/java/org/scrum/psd/battleship/controller`: game logic and ship/position models.
- `src/test/java`: unit, end-to-end, and Cucumber BDD tests.
