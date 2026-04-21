# Rubik’s Cube Solver (Color-Based)

A Python-based Rubik’s Cube solver that takes raw sticker colors as input and computes a solution using the **Kociemba two-phase algorithm**.

This project converts a real-world cube state (based on colors) into a valid internal representation and generates an efficient sequence of moves to solve the cube.

---

## 🚀 Features

* Accepts **raw color input** for all 54 stickers
* Automatically determines face orientation using center pieces
* Validates cube state:

  * exactly 6 colors
  * each color appears 9 times
  * consistent mapping between colors and faces
* Converts color input into **facelet notation** required by the solver
* Generates efficient solution sequences using the **Kociemba algorithm**

---

## 🧠 How It Works

1. **Input Parsing**
   The user provides 54 sticker colors in a fixed order:

   ```
   U, R, F, D, L, B (each face row by row)
   ```

2. **Color Mapping**
   The solver identifies the **center color of each face** and maps it to standard cube notation:

   ```
   U, R, F, D, L, B
   ```

3. **Validation**
   Ensures the cube configuration is valid:

   * exactly 6 distinct colors
   * each color appears exactly 9 times

4. **Transformation**
   Converts the cube into a **facelet string** format required by the Kociemba solver.

5. **Solving**
   Uses the Kociemba two-phase algorithm to compute a solution:

   ```
   Example output: R U R' U' F2 ...
   ```

---

## 📥 Input Format

You must provide **54 characters**, representing the cube:

Example:

```
Enter 9 colors for face U: WWRWWRWWW
Enter 9 colors for face R: RRRRRRRRR
Enter 9 colors for face F: GGGGGGGGG
Enter 9 colors for face D: YYYYYYYYY
Enter 9 colors for face L: OOOOOOOOO
Enter 9 colors for face B: BBBBBBBBB
```

* Each face is entered **row by row**
* Use single-letter colors:

  ```
  W (white), Y (yellow), R (red), O (orange), G (green), B (blue)
  ```

---

## 📤 Example

### Input

```
WWRWWRWWW
RRRRRRRRR
GGGGGGGGG
YYYYYYYYY
OOOOOOOOO
BBBBBBBBB
```

### Output

```
R U R' U' F2 ...
```

(The exact solution will vary depending on the cube state.)

---

## ⚙️ Installation

```bash
pip install kociemba
```

---

## ▶️ Running the Solver

```bash
python speedcube_solver.py
```

Then follow the prompts to enter cube colors.

---

## 📐 Move Efficiency and "God’s Number"

The solver uses the **Kociemba two-phase algorithm**, which produces **highly efficient solutions** in a small number of moves.

In Rubik’s Cube theory, **“God’s Number”** refers to the *minimum number of moves required to solve any cube configuration*.
This value has been proven to be **20 moves or fewer** in the half-turn metric.

While this solver does **not guarantee the absolute optimal (God’s Number) solution**, it consistently generates **near-optimal solutions** that are close to the theoretical minimum.

---

## 🛠️ Tech Stack

* Python
* Kociemba Algorithm
* Data structures (lists, dictionaries)
* Input validation and transformation logic

---

## 💡 Inspiration

Inspired by competitive speedcubing, this project bridges real-world cube states with algorithmic solving techniques, converting raw color input into efficient solution sequences.

---

## 📌 Notes

* The solver assumes a **physically valid cube configuration**
* Invalid color layouts will raise errors
* Solutions are given in standard cube notation:

  ```
  R, U, L, D, F, B, with modifiers like ' and 2
  ```
