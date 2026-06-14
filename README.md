# Scarcity in Cinema

This project supports a thesis about scarcity in cinema:

**Under what conditions does scarcity in cinema operate as a symbolic signal of artistic value and social distinction, rather than simply as a distribution or access constraint?**

The analysis uses movie-level data on theater release size, box office, budget, IMDb ratings, IMDb votes, genre, franchise status, and related variables.

## Main Folders

- `data_final`: final datasets used for the analysis.
- `notebooks`: the main analysis files. These are like digital research documents that contain text, tables, charts, and the code used to create them.
- `figures`: charts and tables created from `exploratory_analysis.ipynb`.
- `figures_analysis`: charts, tables, and regression outputs created from `general_analysis.ipynb`.

You do not need to understand code to read the notebooks. Open the `.ipynb` files and read them from top to bottom like a report.

## Notebook 1: exploratory_analysis.ipynb

File: `notebooks/exploratory_analysis.ipynb`

This notebook is the first broad exploration of the dataset. Its goal is to understand how scarcity appears in the movie data before doing regression analysis.

Contents:

1. **Data quality check**
   - Checks how many movies are in the dataset.
   - Checks missing values, duplicate rows, and important variables.
   - Confirms which variables are usable for the thesis.

2. **Creation of scarcity variables**
   - Creates measures of scarcity using theater counts.
   - Examples include limited release, wide release, platform release, opening theaters, maximum theaters, and theater expansion.

3. **Classification of films by release strategy**
   - Groups films into categories such as exclusive, limited, platform/moderate, semi-wide, and wide release.
   - Shows how common each release type is.

4. **Distribution of opening theaters**
   - Shows how many theaters movies opened in.
   - Helps identify films that started with scarce theatrical access.

5. **Scarcity versus IMDb rating**
   - Compares release scarcity with IMDb ratings.
   - Uses IMDb rating as a rough audience-value proxy, not as a perfect measure of artistic quality.

6. **Scarcity versus box office performance**
   - Compares scarce and wide releases with domestic and worldwide box office outcomes.
   - Helps separate access constraint from possible value-building.

7. **Scarcity versus box-office legs**
   - Looks at whether films had sustained demand after opening weekend.
   - High legs can suggest word of mouth, prestige accumulation, or delayed discovery.

8. **Theater expansion analysis**
   - Studies films that opened small and later expanded to many theaters.
   - This is especially relevant for platform-release scarcity.

9. **Scarcity and ROI**
   - Looks at whether scarce/platform films can be commercially efficient even if they are not the largest box office hits.

10. **Arthouse/prestige versus mainstream/event proxies**
   - Creates rough groups for prestige-style films and mainstream/event-style films.
   - These are only proxies, not perfect labels.

11. **Genre-level scarcity**
   - Compares scarcity patterns across genres.
   - Helps show whether some genres are more connected to limited or platform release strategies.

12. **Time trends**
   - Looks at whether release scarcity has changed over time.

13. **Correlation matrix**
   - Shows relationships between scarcity, box office, IMDb rating, ROI, and legs.

14. **Parasite and Oppenheimer case-study section**
   - Finds both films in the dataset.
   - Shows that Parasite is a strong platform-scarcity case.
   - Shows that Oppenheimer is not scarce by normal theater-count measures because it opened wide.
   - Notes that Oppenheimer's scarcity is mainly about premium formats such as IMAX/70mm, which this dataset does not directly measure.

15. **Final research-question answers**
   - Explains which thesis questions the dataset can answer.
   - Explains which questions need outside evidence, such as marketing materials, festival history, audience discourse, premium-format ticket data, or press coverage.

Saved outputs:

- Charts from this notebook are saved in `figures`.
- Tables from this notebook are saved in `figures` as `.csv` and `.html` files.

## Notebook 2: general_analysis.ipynb

File: `notebooks/general_analysis.ipynb`

This notebook continues the thesis analysis using regression models. Its goal is to test whether scarcity indicators are systematically associated with perceived value, sustained demand, box office, and ROI.

Important note:

The regressions do **not** prove that scarcity causes artistic value or prestige. They show associations in the dataset.

Contents:

1. **Regression dataset construction**
   - Prepares the final dataset for statistical analysis.
   - Creates log-transformed variables for skewed measures such as budget, box office, IMDb votes, and theater counts.
   - Creates scarcity variables such as platform release, limited release, wide release, and theater expansion.

2. **Regression variable checks**
   - Summarizes the variables used in the models.
   - Checks how many films are included.
   - Checks correlations and possible overlap between predictors.

3. **Model specification table**
   - Explains each regression model in plain terms.
   - Shows the dependent variable and purpose of each model.

4. **Model 1: Scarcity and perceived value**
   - Outcome: IMDb rating.
   - Tests whether platform release, opening scale, and expansion are associated with audience evaluation.

5. **Model 2: Scarcity and legs**
   - Outcome: box-office legs.
   - Tests whether scarcity is associated with sustained theatrical demand after opening weekend.

6. **Model 3: Scarcity and worldwide box office**
   - Outcome: worldwide box office.
   - Tests whether scarcity is mostly an access constraint or whether expansion helps later commercial scale.

7. **Model 4: Scarcity and ROI**
   - Outcome: worldwide ROI.
   - Tests whether scarce/platform releases can be commercially efficient.

8. **Model 5: Franchise interaction**
   - Tests whether opening scale works differently for franchise films than for non-franchise films.
   - This connects to the thesis contrast between mainstream event cinema and prestige cinema.

9. **Model 6: Platform release and high rating interaction**
   - Tests whether platform-style scarcity works differently when a film has a high IMDb rating.
   - This supports the idea that scarcity alone may not create value; it may need quality or legitimacy signals.

10. **Model 7: Platform-release likelihood**
   - Tests which types of films are more likely to receive platform-release treatment.
   - Uses a binomial model because the original fixed-effect logistic model was too unstable for the dataset.

11. **Model 8: Quantile regression**
   - Tests whether scarcity matters differently for ordinary films versus higher-performing films.

12. **Model diagnostics**
   - Checks residuals for the main perceived-value model.
   - Helps assess whether the model behaves reasonably.

13. **Parasite and Oppenheimer in the regression context**
   - Shows how both thesis case films appear in the regression variables.
   - Confirms again that Parasite fits platform-release scarcity.
   - Confirms again that Oppenheimer's scarcity is not captured by theater-count scarcity and needs premium-format evidence.

14. **Final thesis interpretation**
   - Translates the regression results back into the thesis research questions.
   - Explains what the models can and cannot support.

Saved outputs:

- Charts from this notebook are saved in `figures_analysis`.
- Tables from this notebook are saved in `figures_analysis` as `.csv` and `.html` files.
- Full regression results are saved in `figures_analysis/regression_results.txt`.
- A cleaned regression dataset is saved in `figures_analysis/regression_dataset_clean.csv`.

## Main Takeaway

The analysis suggests that scarcity is most meaningful when it is not just lack of access. The strongest thesis-relevant pattern is:

**scarce opening + later expansion + strong reception or commercial efficiency**

This pattern fits Parasite well. Oppenheimer is different: it was widely released, so its scarcity is mainly about premium-format access and event status, not ordinary theater-count scarcity.

## Dataset Source

Dataset link:
https://www.kaggle.com/datasets/michaelmatta0/movies-ultimate-metrics-features-and-metadata?resource=download&select=Top+Movies+%28Cleaned+Data%29.csv
