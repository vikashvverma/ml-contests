# Complaint Status Tracking

###  Install

This project requires **Python** and the following Python libraries installed:

- [NumPy](http://www.numpy.org/)
- [Pandas](http://pandas.pydata.org/)
- [scikit-learn](http://scikit-learn.org/stable/)



###Problem Statement

Societe Generale (SocGen) is a French multinational banking and financial services company. With over 1,54,000 employees, based in 76 countries, they handle over 32 million clients throughout the world on a daily basis.

They provide services like retail banking, corporate and investment banking, asset management, portfolio management, insurance and other financial services.

While handling customer complaints, it is hard to track the status of the complaint. To automate this process, SocGen wants you to build a model that can automatically predict the complaint status (how the complaint was resolved) based on the complaint submitted by the consumer and other related meta-data.



### Data Description

The dataset consists of three files: train.csv, test.csv and sample_submission.csv.

| **Complaint-ID**               | Complaint Id                                                 |
| ------------------------------ | ------------------------------------------------------------ |
| **Date received**              | Date on which the complaint was received                     |
| **Transaction-Type**           | Type of transaction involved                                 |
| **Complaint-reason**           | Reason of the complaint                                      |
| **Consumer-complaint-summary** | Complaint filed by the consumer - Present in three languages :  English, Spanish, French |
| **Company-response**           | Public response provided by the company (if any)             |
| **Date-sent-to-company**       | Date on which the complaint was sent to the respective department |
| **Complaint-Status**           | Status of the complaint (Target Variable)                    |
| **Consumer-disputes**          | If the consumer raised any disputes                          |



### Code

The code is provided in the `Complaint_Status_Tracking.ipynb` file. `c3cc8568-0-dataset` directory needs to be present in same folder containingg the extracted `csv` files.



### Run

In a terminal or command window, navigate to the top-level project directory having `Complaint_Status_Tracking.ipynb` and then run one of the following commands:



`ipython notebook Complaint_Status_Tracking.ipynb`

or

`jupyter notebook Complaint_Status_Tracking.ipynb`



This will open the Jupyter Notebook software and project file in your browser.



### Methodology



#### Data Preprocessing



- The data are read into `pandas` data-frame.
- There are 5 types of `Complaint-Status`:
  - Closed with explanation
  - Closed with non-monetary relief
  - Closed
  - Closed with monetary relief
  - Untimely response
- Total number of training records are `43266`
- **Date-received** and **Date-sent-to-company** columns are converted into `duration` column.
- All the non-numeric features are hot-encoded.
- The training data is split into training and testing data.



#### Implementation

- A `BaggingClassifier` model is built with `DecisionTreeClassifier` as base estimator.
- This model is trained on training data and evaluated on testing data.
- The model is then used to predict the `Complaint-Status` for the required test data.
- The predicted values is writtent to the `prediction.csv` file.



The source code is available on [Github](https://github.com/vikashvverma/ml-contests/tree/master/hackerearth/sg)