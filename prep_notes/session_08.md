# Preparation Notes for Session 08
## Avoid Over Engineering
```python
#https://thispointer.com/python-how-to-get-list-of-files-in-directory-and-sub-directories/
def getListOfFiles(dirName):
    # create a list of file and sub directories 
    # names in the given directory 
    listOfFile = os.listdir(dirName)
    allFiles = list()
    # Iterate over all the entries
    for entry in listOfFile:
        # Create full path
        fullPath = os.path.join(dirName, entry)
        # If entry is a directory then get the list of files in this directory 
        if os.path.isdir(fullPath):
            allFiles = allFiles + getListOfFiles(fullPath)
        else:
            allFiles.append(fullPath)
                
    return allFiles
dirName = 'C:\\Users\\jaywang\\Assignment07\CollegeScorecard_Raw_Data';
# Get the list of all files in directory tree at given path
listOfFiles = getListOfFiles(dirName)
```

## Use forward slash ("/") which is cross-platform (works in Windows, Linux, Mac)

```python
os.remove('C:\\Users\\jaywang\\Assignment07\\CollegeScorecard_Raw_Data\\data.yaml')
os.remove('C:\\Users\\jaywang\\Assignment07\\CollegeScorecard_Raw_Data\\Crosswalks.zip')
os.remove('C:\\Users\\jaywang\\Assignment07\\CollegeScorecard_Raw_Data\\a.DS_Store')
os.remove('C:\\Users\\jaywang\\Assignment07\\CollegeScorecard_Raw_Data\\FieldOfStudyData1415_1516_PP.csv')
os.remove('C:\\Users\\jaywang\\Assignment07\\CollegeScorecard_Raw_Data\\FieldOfStudyData1516_1617_PP.csv')
```
## Don't Write Repetitive Code, Use Loops Instead

```python
df1 = pd.read_csv('C:\\Users\jaywang\\Assignment07\\CollegeScorecard_Raw_Data\\MERGED1996_97_PP.csv', usecols = ["UNITID", "INSTNM", "STABBR", "REGION", "ADM_RATE", "TUITIONFEE_IN"])
......
df26 = pd.read_csv('C:\\Users\\jaywang\\Assignment07\\CollegeScorecard_Raw_Data\\MERGED2018_19_PP.csv', usecols = ["UNITID", "INSTNM", "STABBR", "REGION", "ADM_RATE", "TUITIONFEE_IN"])
```