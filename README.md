# decision-tree-classifier-scikit

Python project for
* (i) [Decision Tree Classifier](#decision-tree-clf) using open source scikit-learn library ([examples](#decision-tree-clf-examples))

## Dependencies

The .py project adopts [scikit-learn](http://scikit-learn.org/) - an open source Python library that implements a range of machine learning, preprocessing, cross-validation and visualization algorithms - and [PyDotPlus](pydotplus.readthedocs.io/) - a Python Interface to Graphviz's Dot language.

To install the `scikit-learn` dependency from [Python Package Index](https://pypi.python.org/pypi/pip) (PIP), execute the command in the prompt ```python pip install -U scikit-learn```.

To install the `PyDotPlus` dependency from [Python Package Index](https://pypi.python.org/pypi/pip) (PIP), execute the command in the prompt ```python pip install -U graphviz``` and ```python install -U pydotplus```.

> The [Graphviz](http://www.graphviz.org/) package must also be installed to use some dependent features, such as export PDF and/or PNG based on generated decision tree graph.

> Other dependencies as ```argparse``` and ```csv``` are native to Python platform.

## Contact / License

Feel free to contact me by mail: guilherme.farto@gmail.com

---

<a name="decision-tree-clf"></a>
## Decision Tree Classifier Scikit (decision_tree_clf_scikit.py)
> Based on scikit-learn

Usage:
```python
python decision_tree_clf_scikit.py [-h] [-p PATH] [-c CSV] [-cl CLASSES] [-d DELIMITER] [-q QUOTE] [-e] [-o OUTPUTFILENAME]
```

The arguments shoud be:

`-p PATH, --path PATH` *(optional)*
* path of the directory that contains the data and files

`-c CSV, --csv CSV` *(optional)*
* path of csv file that contains all training data
    
`-cl CLASSES, --classes CLASSES` *(optional)*
* name of csv file (only with classes) that contains all training data. Using this argument implies that the csv file (-c, --csv argument) should not contain the (last) column with classes

`-d DELIMITER, --delimiter DELIMITER` *(optional)*
* delimiter char for CSV file

`-q QUOTE, --quote QUOTE` *(optional)*
* quote char for CSV file

`-e, --export` *(optional)*
* generate and export PDF and PNG with decision tree graph

`-o OUTPUTFILENAME, --outputFileName OUTPUTFILENAME` *(optional)*
* output filename for PDF and PNG files

<a name="all-examples"></a>
## Examples

<a name="decision-tree-clf-examples"></a>
### > Examples for predicting gender (male or female) by decision tree classifier

**Basic usage:**

* **Example #1: XXX**

```python
python decision_tree_clf_scikit.py
```

Output:

xxx

* **Example #2: XXX**

```python
python decision_tree_clf_scikit.py -e
```

Output:

xxx

**Another examples:**

* **Example #3: XXX**

```python
python decision_tree_clf_scikit.py -p c:/data-science
```

Output:

xxx

* **Example #4: XXX**

```python
python decision_tree_clf_scikit.py -e -p c:/data-science
```

Output:

xxx

* **Example #5: XXX**

```python
python decision_tree_clf_scikit.py -c data_without_classes.csv -cl classes.csv
```

Output:

xxx

* **Example #6: XXX**

```python
python decision_tree_clf_scikit.py -c custom-data1.csv -d ;
```

Output:

xxx

* **Example #7: XXX**

```python
python decision_tree_clf_scikit.py -c custom-data2.csv -d ; -q '
```

Output:

xxx

* **Example #8: XXX**

```python
python decision_tree_clf_scikit.py -c custom-data2.csv -d ; -q ' -e
```

Output:

xxx

* **Example #9: XXX**

```python
python decision_tree_clf_scikit.py -c custom-data2.csv -d ; -q ' -e -o myfile
```

Output:

xxx

<a name="additional-information"></a>
## Additional information

<a name="extracting-data-csv-files"></a>
### > Extracting data from CSV files

The Python function ```openCsvFiles()``` is responsible for opening and extracting data from CSV files. This function will return three (3) essential information: `identifiers`, `values`, and `classes`.

* **`identifiers`**: asdf;
* **`values`**: asdf;
* **`classes`**: asdf;

```python
	identifiers, values, classes = openCsvFiles(CSV_FILE, CLASSES_CSV_FILE)

	print "Identifiers ...: %s" % (identifiers)
	print "Values ........: %s" % (values)
	print "Classes .......: %s" % (classes)
```

<a name="export-decision-tree-graph"></a>
### > Export Decision Tree graph (PDF and PNG files)

As mentioned, the `-e, --export` can be used to generate and export PDF and PNG files based on the Decision Tree graph.

> In addition, it's possible to change the default file name by using the `-o OUTPUTFILENAME, --outputFileName OUTPUTFILENAME` argument.
> The default file names are `data_graph.pdf` and `data_graph.png`.

A sample [PDF](example-output-files/data_graph.pdf) and [PNG](example-output-files/data_graph.png) can be visualized using these links.

| data_graph.png           |
| ------------------------ |
| ![](example-output-files/data_graph.png) |

<a name="decision-tree-predict"></a>
### > Predict using the trained Decision Tree

The graph can be used to predict possible outputs to new values after the decision tree training with the original CSV data files.

The .py project is developed to attempt three (3) predictions of examples for new values. For example, the genres (male or female) will be predicted according to the characteristics of `height`, `weight`, and `shoe_size`:

```python
    ## male prediction class
    prediction = clf.predict([[190, 70, 43]])
    print "Prediction for [[190, 70, 43]] = ", prediction

    ## female prediction class
    prediction = clf.predict([[177, 55, 35]])
    print "Prediction for [[177, 55, 35]] = ", prediction

    ## male and female prediction classes
    prediction = clf.predict([[190, 70, 43], [177, 55, 35]])
    print "Prediction for [[190, 70, 43], [177, 55, 35]] = ", prediction
```

Output:

```python
    Prediction for [[190, 70, 43]] =  ['male']
    Prediction for [[177, 55, 35]] =  ['female']
    Prediction for [[190, 70, 43], [177, 55, 35]] =  ['male' 'female']
```
