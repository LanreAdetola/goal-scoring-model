# goal-scoring-model
A machine learning model for predicting player goal-scoring probabilities in football matches, using statistical analysis and logistic regression.

A data-driven approach to predicting whether Tolu Arokodare will score in a given match using Logistic Regression and Expected Goals (xG). The model analyzes match statistics such as shots, xG, key passes, and venue to improve goal prediction accuracy.

📊 Key Takeaways from Your Model
Overall Accuracy → 91.67% ✅

Your model correctly predicted whether the player would score or not in ~92% of test cases.
Class 0 (No Goal Scored)

Precision: 1.00 → Every time the model predicted "No Goal," it was always correct.
Recall: 0.83 → Some instances where the player didn’t score were missed.
Class 1 (Goal Scored)

Precision: 0.86 → When the model predicted "Goal Scored," it was correct 86% of the time.
Recall: 1.00 → It caught all instances where the player actually scored.
Balanced Performance → Both Precision & Recall are strong across both classes, meaning the model is neither too aggressive nor too conservative in predictions. ✅
