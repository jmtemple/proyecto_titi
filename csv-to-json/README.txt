Instructions on how to convert a .xlsx file of tree data to CSV and then JSON format:

1) Download the .xlsx file from Google Sheets as a CSV file (with utf-8 encoding). Can also download
   files from Excel as CSV with utf-8 encoding, and these steps will work the same way. 

2) Move the file to the directory with the files formatCSV.sh and CSVtoJSON.py (or subdirectory).

3) Enter the following commands:

    ./formatCSV.sh path/to/CSVFile/nameOfTreesCSVFile.csv    <--- Or you can manually format the CSV with command line tools yourself

    ./CSVtoJSON.py path/to/CSVFile/nameOfTreesCSVFile.csv path/to/newJSONFile/desiredNameOfTreesJSONFile.json

Now you should have a JSON file with all of the tree data from the original .xlsx file.

NOTE1: Minor manual editing of the CSV file may need to be done before the python script can handle it correctly
       if some data on the .xlsx file does not match up exactly to the what the script is expecting. 

NOTE2: The python script assumes the deathLevel attribute of each tree to be "Nivel 0: Afectación 0 %" when the
       reasonForDeath field is false and "Nivel 4: Afectación > 75 %" when it is non-false. If the reasonForDeath
       field is false (in the CSV) then the script changes it to an empty string because the app will fill in the
       reasonForDeath field with an empty string rather than a false value. 
