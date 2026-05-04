# Rubik’s Cube Solver (Color-Based)

A Python-based Rubik’s Cube solver that takes raw sticker colors as input and generates an efficient solution using the **Kociemba two-phase algorithm**.

This project converts real-world cube color input into a valid internal representation and computes a sequence of moves to solve the cube.

---

## 🚀 Features

* Accepts **raw color input** for all 54 stickers
* Automatically determines face orientation using center pieces
* Validates cube state:

  * exactly 6 colors
  * each color appears 9 times
* Converts color input → **facelet representation**
* Generates efficient solutions using the **Kociemba algorithm**

---

## 🧠 How It Works

1. Input 54 sticker colors in face order (U, R, F, D, L, B)
2. Detect center colors to map faces
3. Validate cube consistency
4. Convert to solver format
5. Generate solution moves

---

## 📥 Input Example

```text
U: WWRWWRWWW
R: RRRRRRRRR
F: GGGGGGGGG
D: YYYYYYYYY
L: OOOOOOOOO
B: BBBBBBBBB
```

---

## 📤 Example Output

```text
R U R' U' F2 ...
```

(The exact solution varies depending on the cube state.)

---

## ⚙️ Installation

```bash
pip install -r requirements.txt
```

---

## ▶️ Run

```bash
python speedcube_solver.py
```

---

## 📐 Move Efficiency and “God’s Number”

This solver uses the **Kociemba two-phase algorithm**, which produces highly efficient solutions.

In Rubik’s Cube theory, **God’s Number** is the minimum number of moves required to solve any cube configuration (proven to be ≤ 20 moves).

While this solver does **not guarantee optimal solutions**, it consistently produces **near-optimal solutions close to the theoretical minimum**.

---

## 🛠️ Tech Stack

* Python
* Kociemba Algorithm
* Data structures and validation logic

---

## 💡 Inspiration
I compete in speedcubing and currently average around 14 seconds on a 3x3. Outside of competition, I've always been curious about what's actually happening algorithmically when a cube gets solved, not just physically but mathematically. By implementing the Kociemba two-phase algorithm, I can to explore the same problem I solve with my hands, but from a computer science perspective.

---

## 📌 Notes

* Input must represent a valid cube configuration (1 Center, 4 Edges, & 4 Coners for each Color)
* Invalid inputs will raise errors
* Output uses standard cube notation:

  * R, U, L, D, F, B
  * ' = counterclockwise
  * 2 = double turn
