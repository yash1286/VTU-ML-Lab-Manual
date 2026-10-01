# Machine Learning Lab Reference

Python scripts and Jupyter notebooks for the VTU seventh-semester computer science machine learning lab. The collection covers basic supervised learning algorithms, CSV-based data preparation, and model prediction.

This repository is a fork of [madhurish/VTU-ML-Lab-Manual](https://github.com/madhurish/VTU-ML-Lab-Manual). It is a learning reference; the upstream implementations are not presented as original portfolio work.

## Included exercises

| Directory | Implementation | Notes |
| --- | --- | --- |
| `Program-1` | Find-S concept learning | Reads the included `finds.csv` |
| `Program-3` | CART decision tree with Gini splits | The filename says ID3, but the implementation is CART; its required banknote CSV is not included |
| `Program-4` | Neural network with backpropagation | Standard-library implementation with an included CSV |
| `Program-5` | Gaussian Naive Bayes from scratch | Legacy Python syntax requires modernization |
| `Program-6` | Gaussian Naive Bayes with scikit-learn | Uses NumPy and the included CSV |
| `Program-9` | k-nearest neighbors classification | Uses scikit-learn's built-in Iris dataset |

The repository also includes notebooks and `manual.pdf`. Only the exercises listed above are present as program directories.

## Run a small example

Install Python 3 and Git, then create an isolated environment:

```bash
git clone https://github.com/yash1286/VTU-ML-Lab-Manual.git
cd VTU-ML-Lab-Manual
python -m venv .venv
```

Activate it with `source .venv/bin/activate` on macOS/Linux or `.venv\Scripts\activate` in Windows Command Prompt, then run:

```bash
python -m pip install numpy scikit-learn
python Program-9/knn-program-9.py
```

This trains a five-neighbor classifier on Iris and prints the predicted class for one example. For Find-S, run from its directory so the relative CSV path resolves:

```bash
cd Program-1
python finds.py
```

Jupyter is optional for opening the notebooks. Package versions are not pinned, and compatibility across the entire collection has not been verified.

## Evaluation and compatibility notes

- Program 6 reports accuracy on the same rows used for training; this is training accuracy, not held-out performance.
- Program 4 normalizes the full dataset before cross-validation. Fit preprocessing on each training fold before using results as an estimate of generalization.
- Program 3 requires the missing `data_banknote_authentication.csv` and a Python 3-compatible CSV loader.
- Program 5 uses `iteritems()` and legacy print formatting.
- These are educational scripts. They do not demonstrate a deployed data pipeline or production ML service.

## Attribution and license

The original MIT license and copyright notice for Madhurish Katta are retained in [LICENSE](LICENSE).
