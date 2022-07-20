---
title: Producing Explainable AI (XAI) and Interpretable Machine Learning Solutions
tags: [Learning, Machine Learning, Artificial Intelligence]
style: fill
color: info
description: Data scientists and machine learning professionals have to stay apace with the latest techniques and approaches in the field. In this course, instructor Keith McCormick shows us how to produce explainable AI (XAI) and interpretable machine learning (IML) solutions.
---

Source: [Keith McCormick](https://www.linkedin.com/learning/machine-learning-and-ai-foundations-producing-explainable-ai-xai-and-interpretable-machine-learning-solutions)

Learn why the need for XAI has been rapidly increasing in recent years. Explore available methods and common techniques for XAI and IML, as well as when and how to use each. Keith walks you through the challenges and opportunities of black box models, showing you how to bring transparency to your models and using real-world examples that illustrate tricks of the trade on the easy-to-learn, open-source KNIME Analytics Platform. By the end of this course, you’ll have a better understanding of XAI and IML techniques for both global and local explanations.

This summarizes the key contents for the course set in LinkedIn Learning on Explainable AI.

## Ways to quantify feature importance
**Global explanations** tell us what input variables are most important to the model. (E.g. GLM coefficient, i.e. the most important variable in the model overall.)
- Partial dependence plots : Show effect of a feature on the outcome (Y = Target, X = Predictor Feature)
- Global surrogates : Surrogate model target variable is the propensity score (prediction) of the black box model
- Permutation feature importance : "Shuffling" the variable randomly to remove any relationship with the target, if error rate increases, then it meant the importance of the shuffled variable

**Local explanations** indicate which inputs were most important to a specific individual prediction (E.g. Reason for specific prediction, such as credit rating score rating)
- SHAP (Shapley Additive exPlanations): Shapley values help to indicate which variables contribute the most (and least) to the model's prediction. High variance = More important
    - Faster and designed to be scalable 
    - Explain the delta
    - Additive
    - More than one version
- LIME (Local Interpretable Model-Agnostic Explanations): Linear model
    - Sample nearby cases
    - Weight closer cases more heavily
- Counterfactuals
    - Attempt to calculate how the target prediction might change if one of the input value changes
    - Measure the effect of a counterfactual by having instances where it is present and where it is absent
- ICE plots
    - Partial dependence plots but for individual cases
One other benefit of XAI is it can tell us that the model appears to produce accurate results, but for the wrong reasons; it will fail on new data.

## Challenges of Variable Importance (VI)
- VIs changes with new variables added even for simple linear regression
- For neural networks, will be near impossible due to how deep it can be. The many layers can result in both positive and negative cases on same variable
- Rashomon effect: Different models, all of them equally good, may give different pictures of relation between predictor and response variables (i.e. different VIs ranking)


## What can we do?
- Awareness helps
- Run VI on more than one model
- Data reduction (reduce multicollinearity)
- Include a transparent model
Reference: Leo Breiman - 'The Two Cultures'
Book to learn more: An Introduction to Statistical Learning (Gareth James, Daniela Witten, Trevor Hastie) - Fig 2.7

## Argument against XAI
- Accuracy is rarely a good reason for complex model
- Black boxes can be harmful
- Black box is easier to keep proprietary
- Use interpretable machine learning, and then you don't need an explanation

## Interpretable Machine Learning
- Feature engineering is critical for IML
- [CORELS (Certifiably Optimal Rule Lists)](https://corels.eecs.harvard.edu/) and recent trends
    - Idea behind CORELS is to search the solution space thoroughly and to produce a compact, yet optimal, set of rules. (address greedy algorithm)
    - Other contemporary algorithms aim for simple solutions and if it competes well with our own complex model, optimisation (simplifying) our model is needed.
- Black box models, especially random forests, can be used to build many models to identify which variables are rarely helpful.

## Personal thoughts
This course quickly summarised the current state of XAI in a beginner-friendly manner and straight to the main point. Of the few examples given, they are on point in cases used such as credit scoring on the COTS tool KNIME.

Due to this course's designation as an intermediate course, it is disappointing that there is no deep explanation in some key areas, such as the working behind local explanations, making it more comparable to an introductory course on XAI. Without concrete examples, some issues regarding feature scaling, imbalance datasets used for credit scoring, and how they affect feature importance remain unclear.

## What's next?
Reading List:
- Interpretable Machine Learning by Christopher Molnar
- XAI authors Scott Lundberg and Marco Ribeiro