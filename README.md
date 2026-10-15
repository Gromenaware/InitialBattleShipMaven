# Battleship

Battleship game for the terminal, written in Java. The player manually places their fleet and plays against a predefined enemy fleet. The interface uses ASCII output and ANSI colors.

## Requirements

- Java 8 or later
- Maven 3.6.3 or later

## Build and run

From the project root:

```bash
mvn clean install
java -jar target/battleship-octubre-*-jar-with-dependencies.jar
```

The build creates a single executable JAR named `battleship-octubre-<timestamp>-jar-with-dependencies.jar`. The timestamp format is `yyyyMMdd-HHmmss`.

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

## License and Support

[![License: CC BY-NC 4.0](https://img.shields.io/badge/License-CC_BY--NC_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc/4.0/) Published by [Agile611](http://www.agile611.com/) under the **Creative Commons Attribution-NonCommercial 4.0 International** license.

README written by [Guillem Hernández Sola](https://www.linkedin.com/in/guillemhs/).

## Contact

- 🌐 [agile611.com](http://www.agile611.com/)
- 📍 Carrer Laureà Miró 309, 08950 Esplugues de Llobregat (Barcelona)
