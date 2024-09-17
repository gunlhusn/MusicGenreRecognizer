<h2>Problem formulation</h2>
The current project aims to build a music genre classifier that would be able to differentiate among five genres: classical, dance, pop, rap, and rock based on different track characteristics (acousticness, danceability, duration, energy, instrumentalness, key, liveness, mode, speechiness, tempo, valence). 

<h2>EDA and data preprocessing</h2>
For the current project, it was decided to generate a database using the Python library for the Spotify Web API. For all mentioned genres several dedicated playlists from Spotify were chosen and audio features for all tracks labeling each with relevant genre extracted. As a result, there were around 3200 data points (more than 600 per genre). After the initial generation, all faulty or repeating rows were dropped. The five-number summary was performed to ensure values were within a reasonable range. Furthermore, feature correlation with genres and other features was analyzed, revealing a high correlation between “loudness”/ “energy” and high negative correlation between “loudness”/”acousticness” attributes, allowing to drop redundant “loudness”. The final step in data preprocessing was MinMax scaling.
  
<h2>Training</h2>
Three ensemble models (Random Forest, Gradient Boosting, XGBOOST) were chosen for the current project. Excessive hyperparameter tuning with the help of GridSearchCV allowed reaching around 80% accuracy on each. Crucial estimators such as precision, recall, f1-score, and confusion matrix were calculated to gain more insight into the results. 

<h2>Arbitary Track Testing</h2>
There is a script for manual check of arbitrary track. In order to see what prediction our models make for any song one should run the last code block and then login into Spotify account with the given credentials (login: aiproject4296@gmail.com, password: AiProjectTeam8User) in the automatically popped out window. Then, a unique song identifier(URI) should be inputted into the console.

Example URI for JID – Sistanem track: spotify:track:6QwJurtbHqyeVda0fhWV2B
