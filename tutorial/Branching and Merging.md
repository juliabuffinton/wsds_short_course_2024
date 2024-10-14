# Tutorial: Branching and Merging

## Create a branch to complete the data cleaning checklist
As data analysts, we often have to clean our data. To make sure we've addressed the most common issues with dirty data, our team has created a common checklist for types of data quality issues to check and address. Let's add that the handbook for easy reference.

Instead of doing this directly on the main version of the handbook, we will create a dedicated branch for development. 

1. Make sure you are starting in the main branch! Do a quick `git status` check or type `git checkout main`. Git bash also shows the branch you're on. There are lots of ways to check!
2. Create a new branch to modify the data cleaning checklist: `git branch data-cleaning-checklist`. 
3. Checkout the new branch using `git checkout data-cleaning-checklist`.
4. Edit the README file (again, using editor of your choice) to add the following checklist items under the `### Data Cleaning Checklist` header:

```
- [ ] Remove duplicates and irrelevant entries.
- [ ] Handle missing data by using appropriate techniques (e.g., mean imputation, deletion).
- [ ] Standardize data formats (e.g., date formats, text case).
- [ ] Detect and treat outliers using appropriate techniques (e.g., remove, transform).
- [ ] Validate the consistency and accuracy of datasets before analysis.
- [ ] Document all data cleaning changes to ensure transparency and reproducibility.
```

5. Save the file, then check status to ensure your modifications are tracked.
6. Stage README for commit by typing `git add README.md`.
7. Commit the changes with a descriptive commit message: `git commit -m "Populated data cleaning checklist"`.

## Merge the branch into main
We're done with our edits, and we're ready to put these changes into production!

1. Switch back to the main branch using `git checkout main`.
2. Merge your changes from the `data-cleaning-checklist` branch by typing `git merge data-cleaning-checklist`.
3. Now that we're done with our edits, delete the branch we created: `git branch -d data-cleaning-checklist`.

## Create a branch for the visualization guidelines, edited by JB
Now, we are going to populate the data visualization guidelines section using a similar workflow. Here, teammates JB and YZ are going to be unknowingly editing the same section. We'll resolve merge conflicts in the next section.

1. Create a new branch and switch to it, this time using one command `git checkout -b jb/data-visualization-guidelines`.
2. Edit the README file to add a few guidelines for data visualization under the `### Data Visualization Guidelines` header:

```
- Use clear and appropriate visualizations for your data (e.g., bar charts, scatter plots).
- Ensure charts are labeled properly with titles, axes labels, and legends.
- Use color schemes that are accessible and highlight key insights.
- Avoid clutter and maintain simplicity in visualizations.
- Maintain consistency in design elements across visualizations.
- Use appropriate scales and intervals for axes.
- Limit the number of categories or data points shown at once.
- Provide context for the data.
```

3. Add the file. 
4. Commit the changes with a descriptive commit message.

## Create a branch for the visualization guidelines, edited by YZ
Now, YZ also created a branch. Here it's very important to make sure that YZ is branching off of the main branch, and not the branch you're currently in (JB's branch).

1. Switch back to the main branch by typing `git checkout main`.
2. Create YZ's branch: `git checkout -b yz/data-visualization-guidelines`.
3. Edit the README file to add one guideline for data visualization under the `### Data Visualization Guidelines` header. Note that this section is empty; JB's changes are in a separate branch and have not been merged in.

```
- Use whitespace effectively to enhance readability and prevent clutter.
```

4. Add the file.
5. Commit the changes with a descriptive commit message.

## Merge in changes; resolve merge conflicts

1. Switch to main: `git checkout main`.
2. Merge in JB's changes: `git merge jb/data-visualization-guidelines`.
3. Try to merge in YZ's changes: `git merge yz/data-visualization-guidelines`. You encounter conflicts!
4. Resolve merge conflicts in your text editor of choice.
5. Add README file; commit with a descriptive message. You've made changes in that tracked file so you will need to add and then commit again.
6. Clean up both branches: `git branch -d jb/data-visualization-guidelines` and `git branch -d yz/data-visualization-guidelines`.