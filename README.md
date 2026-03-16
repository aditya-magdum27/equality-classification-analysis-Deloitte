# Equality Score Classification Analysis

This project was completed as part of the **Deloitte Data Analytics Job Simulation** offered by Forage.

The objective of this project is to analyze workplace equality data and classify equality scores into meaningful categories that help identify fairness levels across different factories and job roles.

---

## Project Objective

Organizations often collect equality-related metrics to evaluate fairness in the workplace.

In this project, the goal was to create a new column called **Equality Class** based on the **Equality Score**.

This classification helps decision-makers quickly identify whether a department or role is operating fairly or showing signs of discrimination.

---

## Dataset

The dataset contains the following fields:

- **Factory** – Workplace location  
- **Job Role** – Role of the employee  
- **Equality Score** – Numerical score indicating fairness level  

The Equality Score ranges across negative and positive values.  
Scores closer to **0** indicate a more balanced and fair workplace environment.

---

## Task Performed

The main task was to create a new column called **Equality Class** which categorizes the Equality Score into three groups.

| Score Range | Equality Class |
|-------------|---------------|
| -10 to 10 | Fair |
| -20 to -11 OR 11 to 20 | Unfair |
| Below -20 or Above 20 | Highly Discriminative |

This classification simplifies interpretation of equality levels within different departments and factories.

---

## Classification Logic

The classification was implemented using Python:

```python
def classify(score):
    if -10 <= score <= 10:
        return "Fair"
    elif -20 <= score < -10 or 10 < score <= 20:
        return "Unfair"
    else:
        return "Highly Discriminative"
