# cs310-csv-json: "CSV/JSON Conversion"
#Project Summary
This project uses two of the standard plain-text data formats that are commonly used for data interchange: Comma-Separated Values (CSV), and JavaScript Object Notation (JSON).  This project creates converters to translate a specific kind of data (course grade data) to and from the CSV and JSON formats.  This project is written in Java 8 and uses Git client and the JUnit testing framework within an IDE.
##
##CSV
##
CSV stands for "Comma-Separated Values", and it is used to represent tabular data.  The particular CSV file used for this project is similar to the following:
##
    "ID","Total","Assignment 1","Assignment 2","Exam 1"
    "111278","611","146","128","337"
    "111352","867","227","228","412"
    "111373","461","96","90","275"
    "111305","835","220","217","398"
    "111399","898","226","229","443"
    "111160","454","77","125","252"
    "111276","579","130","111","338"
    "111241","973","236","237","500"
##
This file represents the grades of eight students (with the given IDs) in a course where there were two assignments and an exam.  The grades listed are represented as strings in the CSV file.  Even though this particular input data contains eight rows (plus the header row), the written code supports an open-ended number of rows.
##
##JSON
##
JSON stands for "JavaScript Object Notation", and it is used as a general-purpose format for many kinds of data, particularly in Web-based applications.  The particular JSON file used for this project is similar to the following (whitespace added for clarity):
##
    {
        "colHeaders":["ID","Total","Assignment 1","Assignment 2","Exam 1"],
        "rowHeaders":["111278","111352","111373","111305","111399","111160","111276","111241"],
        "data":[[611,146,128,337],
                [867,227,228,412],
                [461,96,90,275],
                [835,220,217,398],
                [898,226,229,443],
                [454,77,125,252],
                [579,130,111,338],
                [973,236,237,500]
        ]
    }
##
This file represents the exact same data as the CSV file above; it is just organized differently.  The "rowHeaders" and "colHeaders" values are lists of strings, and the "data" value is a list of integer lists.  The grades in the "data" portion of the JSON file are represented as integers instead of strings, while the "rowHeaders" are represented as strings instead of integers.
##
#Running the Program
The program requires Java 8, Netbeans (IDE), JSON simple library, and open CSV library to run.
To execute the program fork and clone the GitHub repository: clone this repository using the Git client built in to the NetBeans IDE.
While creating the project in NetBeans, use the "Java Project with Existing Sources" option to keep the source files under version control separate from the NetBeans project files.
Download and install the OpenCSV and json-simple libraries.
Finally, check the NetBeans project that was cloned from GitHub to ensure that the necessary libraries are included in its classpath.  In the NetBeans project tree, right-click the project name, select "Properties", and in the "Project Properties" tree, choose "Libraries" from the list of categories.  Ensure that there are four compile-time libraries added to the project: OpenCSV, json-simple, JUnit 4.x, and Hamcrest 1.x (Hamcrest is a framework for writing "matcher" rules; it is required by JUnit).  If any libraries are missing, click "Add Library" and add them from the list of libraries.  Click "OK" to commit changes.


#Classes Documentation
Cs310-csv-json contains 3 classes, one of which is a test class.
________________________________________
##Class: Converter
________________________________________
This class holds all of the information for the two conversion method: csvToJson() , which converts a CSV string to the corresponding JSON string, and jsonToCsv(), which converts a JSON string into the corresponding CSV string.
##
##Class: Main
________________________________________
This is a main class of the project that communicates with Convertor class and uses toString() method to get string from StringBuilder which is created in the class.
##
##Class: ConverterTest
________________________________________
This is a test class for the given project. To run the unit tests, right-click ConverterTest class and choose "Run File" from the context menu.  A new output window should appear which displays the results of all unit tests.  If the converter methods are functioning correctly, the resulting strings should exactly match the original data from the input files.
