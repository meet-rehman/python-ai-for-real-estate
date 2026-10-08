# Python and AI for Business and Real Estate Students

Classroom notebooks that take a student with no programming background from a first `print()` to a working image classifier.

I developed them in 2026 as a research assistant (HiWi) for the Python and AI course of Prof. Dr. Burkhard Hoppenstedt at HfWU Nürtingen-Geislingen (Forschungsbereich Wirtschaft und Recht), and I assisted the students in class.

Each notebook is one classroom session: a short explanation of the idea, worked code with real data, and exercises for the students.

## Modules

| # | Notebook | What students build | Data | Open |
|---|---|---|---|---|
| 0 | [Python Fundamentals](Module_0_Python_Basics.ipynb) | The basics: data types, control flow, functions, data structures, files and JSON, regular expressions, APIs, classes, coding practice | Small business examples written into the notebook | [Colab](https://colab.research.google.com/github/meet-rehman/python-ai-for-real-estate/blob/main/Module_0_Python_Basics.ipynb) |
| 1 | [Sentiment Analysis](Module_1_Sentiment_Analysis.ipynb) | A text classifier that labels tweets as positive, neutral or negative | TweetEval, about 60,000 real tweets | [Colab](https://colab.research.google.com/github/meet-rehman/python-ai-for-real-estate/blob/main/Module_1_Sentiment_Analysis.ipynb) |
| 2 | Sales Forecasting | A model that forecasts monthly retail sales from past months | US monthly retail sales from FRED | To be added |
| 3 | [Computer Vision](Module_3_Computer_Vision.ipynb) | A model that recognises the room type in a property photo | MIT Indoor Scenes, 6 room types | [Colab](https://colab.research.google.com/github/meet-rehman/python-ai-for-real-estate/blob/main/Module_3_Computer_Vision.ipynb) |

## What each module teaches

**Module 0: Python Fundamentals** (90 to 120 minutes)
Nine short parts with business examples such as VAT, break-even and inventory value, followed by four exercises. It ends with coding style, reproducibility and error handling.

**Module 1: Sentiment Analysis** (75 to 90 minutes)
Cleaning social media text, TF-IDF, four handcrafted features, a Naive Bayes classifier and an sklearn Pipeline. The model is trained on a 5,000-tweet sample for classroom speed and reaches 50.7% accuracy on 12,284 held-out tweets across three classes. That weak result is kept on purpose. The session is about reading it: the confusion matrix shows that the model misses most negative tweets, and the students work out why.

**Module 2: Sales Forecasting** (75 to 90 minutes, to be added)
Trend and seasonality, date features, cyclical encoding, lag and rolling features, a split by date instead of a random split, linear regression, and a recursive forecast for the next three months. A section on reading coefficients explains why features on different scales cannot be compared directly.

**Module 3: Computer Vision** (75 to 90 minutes)
Images as arrays of numbers, then three models on the same task so the students see what each step adds:

| Model | Test accuracy |
|---|---|
| Logistic regression on raw pixels | 29.4% |
| Small CNN trained from scratch | 41.6% |
| MobileNetV2 with transfer learning | 74.2% |

Trained on 1,890 images and tested on 279. Two of the six classes have fewer than ten test images, which the notebook points out.

## How the notebooks are built

- Every step has a plain-language explanation before the code.
- Results are reported as they came out, including the weak ones, and the students are asked to explain them.
- Train and test data are kept apart, and each module says how.
- Modules 1 to 3 end by packaging the model as a pipeline or a saved file, so it could be reused.
- Every module closes with exercises.

## Running the notebooks

**Google Colab (recommended).** Use the Colab links in the table. Module 3 trains much faster with a GPU: Runtime, Change runtime type, T4 GPU.

**Locally.**

```
pip install -r requirements.txt
jupyter notebook
```

Notes:

- The interactive Plotly charts do not show in the GitHub preview. Open the notebook in Colab or Jupyter to see them.
- Module 1 contains one cell that downloads a file through Colab. Skip it when running locally.
- The data is downloaded when a notebook runs. No dataset is stored in this repository.

## Data and credits

| Used in | Source |
|---|---|
| Module 1 | TweetEval sentiment dataset (Barbieri et al., 2020), `cardiffnlp/tweet_eval` on HuggingFace |
| Module 3 | MIT Indoor Scenes (Quattoni and Torralba, 2009), HuggingFace version `keremberke/indoor-scene-classification`. The sample photos shown in the notebook outputs come from this dataset. |
| Module 3 | MobileNetV2 (Sandler et al., 2018), ImageNet weights from Keras |

## Author

Abdul Rehman, [github.com/meet-rehman](https://github.com/meet-rehman)

Course: Python Programming and AI, Prof. Dr. Burkhard Hoppenstedt, HfWU Nürtingen-Geislingen.
