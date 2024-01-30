# Assignment 2. Supervised Learning. AI.

## Final Delivery

- David Burchakov (up202203777@edu.fe.up.pt)

#### To run the program, open *Project_2_Supervised_Learning.ipynb* file with Jupyter Notebook.

## Description

*To see a more detailed description and the result, open the .ipynb file*


Application of different Machine Learning algorithms, including Nearest Neighbor, SVM, Decision Trees and Neural Networks and a comparison of theese algorithms. The purpose of the project is to find a binary solution for real-life data - 
[Regensburg Pediatric Appendicitis](https://zenodo.org/records/7711412) dataset. 
Machine Learning algorithms are taught to identify, whether an entry will have apendicitis or not based on his characteristics.

### Steps

#### I. Correct the data
Firstly, the data should be corrected from erroneous data, empty entries or outliners.

Remove outliers

![outliner](docs/outliner.png)
*outlier

Remove erroneous data
~~~~
# - remove anomally tall babies
rows_to_drop = data[(data['Age'] <= 3.0) & (data['Height'] > 100)].index
dataNew = data.drop(rows_to_drop)

# - remove anomally cold patients
rows_to_drop = dataNew[(dataNew['Body_Temperature'] <= 30)].index
dataNew = dataNew.drop(rows_to_drop)

# - remove anomally big RDW
rows_to_drop = dataNew[(dataNew['RDW'] > 30)].index
dataNew = dataNew.drop(rows_to_drop)

# Remove anomaly heavy children (aged less than 3 years)
rows_to_drop = dataNew[(dataNew['Age'] < 2) & (dataNew['Weight'] > 14.8)].index
dataNew = dataNew.drop(rows_to_drop)
~~~~

Additionally, we remove columns with incremental unique unformation that does not affect the final binary solution
![US_number](docs/US_number.png)

*US_number is an incremental unique number of the patient that does not influence having appendicitis or not.*

#### II. Analyse the data

In order to anylise the data, we can make a *Heatmap graph* that indicates the correlation between each characteristic (column) 
and desired result (having appendicitis: yes/no) and drop those columns that do not affect the result.

![heatmap](docs/heatmap.png)


#### III. Apply Machine Learning Algorithms

**Algorithms applied:**

a) Nearest Neighbor

b) SVMs

c) Decision Trees

d) Neural Network
