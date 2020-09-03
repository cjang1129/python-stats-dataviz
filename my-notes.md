# Assignment #1

```

for year in years:
path = '/Users/masoud/Downloads/names/yob%d.txt' % year
frame = pd.read_csv(path, names=columns)

```

You would need to indent within the for loop:

```
for year in years:
    path = '/Users/masoud/Downloads/names/yob%d.txt' % year
    frame = pd.read_csv(path, names=columns)
```

```
import json
path = 'ch02/usagov_bitly_data2012-03-16-1331923249.txt' 
records = [json.loads(line) for line in open(path)]
```

This is a common issue related to absolute path vs relative path. also need to know what is your current path. 

# For Session #2
- Brief self-introduction of the students who did not get a chance to speak.
- Q & A regarding the assignment #1 and the course in general
    - Text book: SECOND edition 
- Lay out rules for assignment submission
    - Two days grace period after the due day
    - Lose half of the total points after the grace period 
    - Exception: Communicate prior to the original due day with legitimate reseasons. 
- Python environments
    - Show the free env list
    - pythonanywhere.com
    - Google Colab
- Python Fundamentals 
    - Show the Python summary first 
      Data types
    - Inputs/outputs
    - Functions
- Assignment #2