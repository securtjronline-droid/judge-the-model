# Decisions

<!-- Fill in each section at the step the activity website gives, then commit and push.
     Write each answer after its label. Keep the headings and labels exactly as they are:
     `python -m analysis` reads them. Limit: 150 words for Before results.
     Fill in Recommendations and Design choice and AI use last, once your app is built. -->

## Before results
For each dataset: positive class; which error matters more for the job (missed positive or false alarm) and why.

- readmission: For hospital readmission, I would prioritize balancing false negatives and false positives. Missing a patient who needs additional follow-up care could lead to a preventable readmission, but incorrectly identifying too many patients as high-risk could waste limited hospital resources. I would want a model that identifies patients who need support without creating an unreasonable number of unnecessary interventions.

- diabetes: For diabetes screening, I would prioritize balancing false negatives and false positives. A false negative could delay diagnosis and treatment for someone with diabetes, while a false positive could lead to unnecessary testing, costs, and anxiety. I would want the model to identify people who may need further testing while keeping unnecessary referrals at a reasonable level.

## Recommendations

- readmission: I recommend the random forest model for hospital readmission because it achieved the highest test AUROC (0.6521) among the models evaluated. However, its performance is still modest, so I would recommend further evaluation before using it in patient care. I would also examine false positives and false negatives to balance patient safety and hospital resources.

- diabetes: I recommend logistic regression for diabetes screening because it achieved the highest test AUROC (0.8266) among the models evaluated. It is also easier to interpret and explain than more complex models. Before using it in clinical practice, I would evaluate its false positive and false negative rates and validate its performance on additional patients.

## Design choice and AI use

- design choice: My design choice was to prioritize a balance between false positives and false negatives for both hospital readmission and diabetes screening. I made this choice because false negatives can cause patients who need care to be overlooked, while false positives can lead to unnecessary testing, interventions, and use of healthcare resources.

- AI suggestion I turned down: One AI-presented option I did not choose was random forest for diabetes screening. I chose logistic regression instead because it had a slightly higher test AUROC (0.8266 compared with 0.8232) and was easier to interpret. I decided that both predictive performance and explainability were important for this healthcare application.