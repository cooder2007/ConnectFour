# Connect Four vs an ANN

## Files
| File | What it is |
|---|---|
| `connect4_ann.ipynb` | Main notebook: load dataset, explore, train the ANN, evaluate, save, play |
| `connect4_dataset.csv` | ~70k Connect Four positions + best column (label), made by `generate_dataset.py` |
| `engine.py` | Game rules (bitboards), minimax "teacher", ANN agent |
| `generate_dataset.py` | Re-creates the dataset: `python generate_dataset.py --rows 30000 --depth 5` |
| `play.py` | Play vs the ANN (window or `--console`) |
| `connect4_ann.joblib` | Already-trained model (the notebook re-creates it) |

## Setup
Python 3.10+ and: `pip install numpy pandas scikit-learn matplotlib joblib jupyter`

## Run
1. Open `connect4_ann.ipynb` and run all cells (training takes a couple of minutes).
2. Play: `python play.py` (window) or `python play.py --console`.
   Options: `--ai-first`, `--pure` (ANN only, no win/block rule).

## Dataset format
`c00`...`c41` = board cells (row-major, top row first) from the view of the player to move
(+1 mine, -1 opponent, 0 empty); `best_move` = column 0-6 chosen by depth-5 minimax.
