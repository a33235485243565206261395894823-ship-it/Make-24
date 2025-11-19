# Make-24 | Solver & Generator
A fully offline web-based tool for solving and generating Make-24 (24-game) puzzles

## How-to-Use
1. Download .html file
2. Open in any modern browser
3. Select "Card Generator" or "Solver" fuction

### Card Generator
4. "Card Generator" - Select desired function (Ace-10, Ace-King, or Ace-Joker)
5. "Card Generator" - Press the "Generate" button
6. "Card Generator" - View the four generated cards (Ace is shown as "A"; Jack, Queen, and King are shown as "J", "Q", and "K" respectively with marks under with 11, 12, and 13 respectively; Joker is shown as "J")
7. "Card Generator" - Press the "Show Solution" button to show all possible solutions (or one possible solution if there are 3 or more Jokers)
8. "Card Generator" - Press the "Hide Solution" button to hide solutions

### Solver
9. "Solver" - Enter 4 numbers (1 for Ace, 11 for Jack, 12 for Queen, 13 for King, and "J" for Joker)
10. "Solver" - Press the "Solve" button
11. "Solver" - View all possible solutions (or one possible solution if there are 3 or more Jokers)
12. Close the tab when finished

## Features
1. **Solver**: Find all possible solutions for any 4 numbers (1-13 and Joker)
2. **Card Generator**: Generate guaranteed solvable 4-number card sets
3. **Joker Support**: Handle wild cards with intelligent brute-force and lookup algorithms for solver and card genrator
4. **Clean UI/UX**: Easy to use and learn
5. **Three Card Types**: Ace-10 (A-10; 1-10); Ace-King (A-K; 1-13); Ace-Joker (A-J; 1-J)
6. **Show All Solutions**: Shows all solutions for all cards, or one possible solution if there are 3 or more Jokers
7. 

## Technical Details
1. **Pure HTML/CSS/JavaScript** - No external dependencies
2. **Fully Offline** - Works without internet connection
3. **Fast Performance** - Solutions computed in milliseconds (times out in 30 seconds)
4. **Smart Joker Handling**:
  - 1-2 Jokers: Brute-force all combinations (1-13)
  - 3 Jokers: Precomputed lookup table
  - 4 Jokers: Preset answer with note
5. Solutions are sorted by complexity (fewest operations first)

## Algorithms
The solver evaluates all permutations of:
1. 4 numbers
2. 4 operations (+, -, ×, ÷)
3. All valid parentheses groupings

*End of Document*
