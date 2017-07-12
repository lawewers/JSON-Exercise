
# JSON EXERCISE

This was an exercise completed for my Data Intensive course conducted by Springboard. The objective of this exercise is to practice using JSON files, normalizing data, and dataframe manipulation to answer questions.

<h3>QUESTIONS</h3>
Using data in file 'data/world_bank_projects.json' and the techniques demonstrated above,
1. Find the 10 countries with most projects
2. Find the top 10 major project themes (using column 'mjtheme_namecode')
3. In 2. above you will notice that some entries have only the code and the name is missing. Create a dataframe with the missing names filled in.

<h3>ANSWER 1</h3>
To answer the first question I loaded a json file the was provided to answer the questions as a pandas dataframe. This allowed me to acquire the information needed to answer the first question. I narrowed down the dataset to only view the country names. Next I used a ``.value_counts()`` function to count the amount of times a country appears in the dataset. A benefit to using this function is it automatically orders the countries by greatest number of times counted to least. With the dataset already in numerical order, the ``.head()`` function allows me to view the first few rows. The default is to show the first five rows. To adjsut the number of rows shown to ten, a 10 is placed in the parentheses.

<h3>ANSWER 2</h3>
To answer the second question the json file provided needed to be loaded as a string. The 'mjtheme_namecode' column needed to be normalized. Normalizing the major theme column allows me to view the theme code and name as a dataset. I normalized the dataset with the following code:
``json_normalize(df1, 'mjtheme_namecode')``
After normalizing the data, I was able to use the same strategy from the first question to find the top ten major themes used.

<h3>ANSWER 3</h3>
The dataset provided had missing 'name' values under the 'mjtheme_namecode' column. I wanted to replace the missing names with "Unknown Name". I used the ``.replace()`` function on the normalized data set to replace the missing names in the following code:
``major_theme.replace({'name':''}, {'name':'Unknown Name'})``
I then repeated the code for answer 2 but using the revised dataset to include the new replaced value "Unknown Name".
# JSON-Exercise
