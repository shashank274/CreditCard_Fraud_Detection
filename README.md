# Credit Card Fraud Detection

A logistic regression model that flags fraudulent credit card transactions. The main challenge is that fraud is very rare: in this data there are 578 normal transactions for every fraudulent one.

Built with Python, pandas and scikit-learn in a Jupyter notebook.

## The data

The notebook uses the public credit card fraud dataset (European cardholders, `creditcard.csv`):

- **284,807 transactions**: 284,315 normal and 492 fraudulent
- **Time**: seconds since the first transaction
- **V1 to V28**: features already anonymised with PCA
- **Amount**: transaction amount
- **Class**: 0 = normal, 1 = fraud

There are no missing values.

## What the notebook does

1. **Explores the data.** Compares normal and fraudulent transactions. For example, the average fraudulent amount (about 122) is higher than the average normal one (about 88).
2. **Balances the classes by undersampling.** A model trained on the raw data could score 99.8% accuracy just by calling everything "normal". So the notebook takes a random sample of 492 normal transactions and combines it with all 492 frauds, giving a 50/50 dataset of 984 rows.
3. **Splits the data** 80/20 into training and test sets, stratified so both keep the 50/50 balance.
4. **Trains a logistic regression model.**
5. **Evaluates it** with accuracy and an ROC curve.

## Results

| Set | Accuracy |
| --- | --- |
| Training | 94.92% |
| Test | 92.39% |

Because the test set is balanced, 92.39% means the model is genuinely telling fraud and normal apart, and not just guessing the majority class.

## Ideas to improve it

- Report precision, recall and F1 as well as accuracy, since missing a fraud costs more than a false alarm
- Scale `Time` and `Amount` before training
- Try SMOTE instead of undersampling, so fewer normal transactions are thrown away
- Compare with tree models such as Random Forest or XGBoost

## Run it

```bash
git clone https://github.com/shashank274/CreditCard_Fraud_Detection.git
cd CreditCard_Fraud_Detection
pip install -r requirements.txt
```

Download `creditcard.csv` (the Kaggle "Credit Card Fraud Detection" dataset), put it in this folder, then open `model.ipynb` in Jupyter.

---

More of my work: [shashank-k.vercel.app](https://shashank-k.vercel.app)
