# Lesson 1 - Read CSV

Rx Open provides a CSV of pharmacies along with their addresses and locations.

The goal for today is to learn how to read the CSV file and parse the data in it. Eventually, we will be able to use the location data in the CSV to plot the locations of each pharmacy on the map.

### 0. Environment Setup

- [ ] Make sure that `git` is installed or use [glitch](glitch.com)
- [ ] Make sure that `python` is installed
- [ ] Make sure that the Python library `pandas` is installed
- [ ] Make sure that you have Jupyter setup

### 1. Download Pharmacy Data

Rx Open provides a CSV of pharmacies along with their addresses and locations.

Download the data for this assignment into the directory for this assignment.

https://hifld-geoplatform.opendata.arcgis.com/datasets/pharmacies

### 2. Create Python Script

Create a Python script called `main.py` in the directory for this assignment.

Have the script print out something like `"Hello World"`, and then run:

```
python main.py
```

Your script should print out the message that you told it to!

### 3. Reading a File

Python provides an `open` function for reading files. ([Read more about `open()`](https://docs.python.org/3/library/functions.html#open))

To open a file, you can pass in the filename as an argument. For example:

```
my_file = open('filename.csv')
```

### 4. Getting Content from a File

Opening a file lets us read contents from the file or also write to the file. For this exercise, we will just look at reading from a file.

Python gives you a few ways you can read content from a file. You can read the entire file with `read()`:

```
file_contents = my_file.read()
```

Alternatively, you can read in a file line-by-line with `read_lines()`:

```
file_contents = my_file.read_lines()
```

Try both, and see what each gives you!

### 5. Closing a File

After we are done with the file, we always want to make sure that we close it:

```
my_file.close()
```

We should close any files we use so that other programs can use the file after us.

### 6. Parsing CSV Data

When we read data from a file, it gets stored as a string. While you can do a lot with a string, it's hard to get specific pieces of data. For example, if we wanted to know the State of a pharmacy address, how would we do that with a string?

In order to surface that information more easily, we need to "parse" the string data from the CSV file.

CSV stands for "(C)omma (S)eparated (V)alues", so if we "split" the data into pieces at each comma, we can extra the individual fields.

Python provides a function for splitting strings, which we can leverage here:

```
parsed = line.split(',')
```

- What does the parsed data look like?
- How can we parse every line of the CSV file?
- What happens if there's a "comma" inside a field?

### 7. Using Pandas to Read a CSV

Luckily for us, `pandas` provides a very simple way of reading CSV data with the [`read_csv()`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.read_csv.html) function.

First, to use `pandas`, you'll have to import it!

```
import pandas
```

Like `open()`, `read_csv()` takes in the filename as an argument:

```
csv = pandas.read_csv('filename.csv')
```

`pandas` will know how to turn the file contents into Python objects, which makes the data much easier to work with.

### 8. Using Jupyter Notebook

Create a new Notebook in Jupyter, and copy the `pandas` code for next time!
