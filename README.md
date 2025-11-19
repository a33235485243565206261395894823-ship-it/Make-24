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
7. **Impossible**: Shows if there is no solution to answer

## Technical Details
1. **Pure HTML/CSS/JavaScript** - No external dependencies
2. **Fully Offline** - Works without internet connection
3. **Fast Performance** - Solutions computed in milliseconds (times out in 30 seconds)
4. **Smart Joker Handling**:
  - 1-2 Jokers: Brute-force all combinations (1-13)
  - 3 Jokers: Precomputed lookup table
  - 4 Jokers: Preset answer with note
5. Solutions are sorted by complexity (fewest operations first)
6. "Joker" and "Wild Card" are interchangable terms ("Joker" is used in the Solver and Generator dropdown while it is referred to as a "Wild Card" in the Generator output; it is referred to as "W" in the computation"

## Algorithms
The solver evaluates all permutations of:
1. 4 numbers
2. 4 operations (+, -, ×, ÷)
3. All valid parentheses groupings

*End of Document*






## Reading the Output

### Solution Format
Solutions are displayed as mathematical expressions that equal 24 (Examples of Addition, Subtraction, Multiplication, and Division, respectively)
```
1+2+3+4 = 10
9-3-2-1 = 3
1*2*3*4 = 24
48/4/3/2 = 2
```

### Parentheses Rules
- Parentheses indicate order of operations (follow standard order of operations)

**Example:** `(1 + 5) * 4 = 24`
1. First: `1 + 5 = 6`
2. Then: `6 * 4 = 24`

### Joker/Wild Card Solutions
When using Jokers (wild cards), solutions show which values were assigned:

**Format:** `W(x)` indicates the wild card was set to that value
**Example:** `w(1)` indicates the wild card is an Ace

### Computation Time
In Solver mode, computation time is displayed in milliseconds (ms):
```
Computed in 15ms    ← typical
Computed in 2500ms  ← Complex cases
```

### Numeric Examples
**Ace to Ten Operations**
```
8 * (5 - 8 / 4) = 24
(5 - 8 / 4) * 8 = 24
4 * (5 + 8 / 8) = 24
(5 + 8 / 8) * 4 = 24
4 * (8 / 8 + 5) = 24
```
**Ace to King Operations**
```
1 + 2 + 9 + 12 = 24
9 + 12 + 1 + 2 = 24
12 + 9 + 1 + 2 = 24
9 + 1 + 2 + 12 = 24
1 + 2 + 12 + 9 = 24
```

## Wild Card Examples
**Single**
```
4 * 3 * 2 * W(1) = 24
2 * W(1) * 4 * 3 = 24
4 * 3 * 2 / W(1) = 24
2 / W(1) * 4 * 3 = 24
W(1) * 2 * 4 * 3 = 24
```
The wild card is assigned a 1
**Double**
```
(W(1) + 1) * 4 * W(3) = 24
4 * W(3) * (W(1) + 1) = 24
W(3) * (4 * (W(1) + 1)) = 24
(4 * (W(1) + 1)) * W(3) = 24
(W(1) + 1) * W(3) * 4 = 24
```
The first wild card is assigned a 1 while the second is a 3
**Triple**
```
hello world
```
**All**
```
1 * 2 * 3 * 4 = 24 = 24
```
This is the default if four cards are wild because there is a large amount, this is only one solution
