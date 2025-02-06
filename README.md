# YouTube Comment Spam Detection

This project demonstrates how to use machine learning to classify YouTube comments as spam or not spam. The classification is based on text features extracted from the comment content in Azerbaijani

## Libraries Used

- `pandas`: Data manipulation and analysis
- `matplotlib` & `seaborn`: Data visualization
- `scikit-learn`: Model building and evaluation

## Dataset

The dataset consists of YouTube comments with the following columns:
- `COMMENT_ID`: Unique identifier for the comment
- `AUTHOR`: Comment author's name
- `DATE`: Comment date
- `CLASS`: 0 for non-spam, 1 for spam
- `CONTENT_az`: The comment text

### Sample Data:
| COMMENT_ID | AUTHOR        | DATE                 | CLASS | CONTENT_az                                |
|------------|---------------|----------------------|-------|-------------------------------------------|
| 345        | Carmen Racasanu | 2014-11-14T13:27:52 | 0     | Planetdə yalnız mən olduğum halda bunun necə 2... |
| 346        | diego mogrovejo | 2014-11-14T13:28:08 | 0     | 2014-cü ildə buna niyə baxdığımı indi bilmirəm |
| 347        | BlueYetiPlayz | 2015-05-23T13:04:32 | 1     | Call of duty videoları və Hədəf-100 abunələri ... |

## Data Preprocessing

- Removed irrelevant columns (`COMMENT_ID`, `AUTHOR`, `DATE`, `non_letter_count`)
- Converted text to lowercase
- Vectorized text using `TfidfVectorizer`

## Model

A Naive Bayes classifier (`MultinomialNB`) is used for spam detection.

- **Training Accuracy**: 99.29%
- **Test Accuracy**: 95.71%

## Spam Detection Example

Given the input:

```text
Bu videoya baxın və dərhal 1000 manat qazanmaq şansını əldə edin! Linkə klikləyin!
