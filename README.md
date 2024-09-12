# Machine_Learning_Models

## Linear Regression Model:
### Equation:
  - **$ŷ = b_0 + b_1X_1$** ⇒ simple line equation.
  - **ŷ** ⇒ is the Dependent Variable to be predicted.
  - X1 ⇒ is the Independent Variable to work as a predictor.
  - b0 ⇒ y-intercept(constant).
  - b1 ⇒ slope coefficient.
### How do we know which of the sloped lines is the best ?
  - Ordinary Least Squares method:
    - How it works ?
      - for each linear regression line ⇒ project all data points on it ⇒ for each data point(x , y) where y is the actual amount of the target and it’s projection point(x , **ŷ**) where ŷ is the predicted amount of the target ****on the line ⇒ both are at the same x ⇒ So, to get the best line ⇒ the Ordinary Least Squares get the line which has the minimum sum of all squared differences between yi and ŷi ⇒ line with SUM(yi - ŷi)^2 is minimized for all data points ⇒ i represents the current data point.

# --------------------------- --------------------------- --------------------------- ---------------------------

## Multiple Regression Model:
### Equation:
  - $ŷ = b_0 + b_1X_1 + b_2X_2 + …. + b_nX_n$
  - ŷ ⇒ the dependent variable.
  - b0 ⇒ y-intercept.
  - b1 ⇒ slope coefficient 1 , X1 ⇒ independent variable 1
  - b2 ⇒ slope coefficient 2 , X2 ⇒ independent variable 2
### What are the 5 methods of feature selection building models ?
  - 1. All-in(Full model):
      - Include all variables in the model without any feature selection. This method is useful when you have domain knowledge that suggests all variables are important or when you want to avoid bias in selecting variables.
      - **Steps**:
        - 1. Fit the model with all predictors and don't remove any variables.
  
  - 2. Backward Elimination(stepwise regression)
      - **Process**: Start with all independent variables in the model. At each step, remove the variable with the highest p-value (i.e., the least statistically significant), as long as it's greater than a significance level (e.g., 0.05).
      - **Steps**:
        1. Fit the model with all predictors.
        2. Remove the predictor with the highest p-value if it's above the threshold.
        3. Repeat until all remaining predictors have p-values below the significance level.

        > once the P-value is < SL(statistical level) ⇒ FINish and fit the model then the model is ready.
        The **p-value** of each variable represents the probability that the coefficient of that variable is not statistically significant in the regression model. In other words, it shows how likely it is that the relationship between the independent variable (predictor) and the dependent variable (outcome) is due to chance.
        > 
        - **Low p-value (< 0.05)**:
            - Indicates strong evidence against the null hypothesis, meaning that the variable is **statistically significant** and likely has a genuine relationship with the dependent variable.
            - In backward elimination, a variable with a low p-value is kept in the model.
        - **High p-value (> 0.05)**:
            - Suggests that there is a **weak relationship** between the independent variable and the dependent variable, and the variable may not be contributing much to the model's predictive power.
            - Variables with high p-values are typically removed from the model during backward elimination.
        
        #### What the p-value represents in backward elimination ?
          - It indicates how confident we are that the coefficient for each independent variable is different from zero (i.e., that the variable has an impact on the outcome).
          - If the p-value is greater than a threshold (commonly 0.05), we assume that the variable does not significantly contribute to the model and is likely included due to random chance.

    - 3. Forward Selection(stepwise regression)
        - **Process**: Start with no variables in the model. Add the most significant variable (the one with the lowest p-value) at each step until no more variables can be added that improve the model significantly.
        - **Steps**:
            1. Start with no predictors.
            2. Add the predictor that most improves the model.
            3. Repeat until no predictor improves the model beyond the chosen significance level.

    - 4. Bidirectional Elimination(stepwise regression)
        - **Process**: A combination of forward selection and backward elimination. Variables are added in the model one by one (like forward selection), but after each addition, the model checks if any existing variables can be removed (like backward elimination).
        - **Steps**:
            1. Start with no predictors.
            2. Add the predictor that most improves the model.
            3. Check if any existing predictors can be removed.
            4. Repeat until no more variables can be added or removed.
        
    - **5.** All Possible Subsets (Exhaustive Search):
        - **Process**: This method involves fitting models for every possible combination of the independent variables and selecting the one that performs best based on some criterion (like R-squared, AIC, or BIC).
        - **Steps**:
            1. Generate all possible subsets of independent variables.
            2. Fit a model for each subset.
            3. Select the model with the best performance according to the chosen criterion.

# --------------------------- --------------------------- --------------------------- --------------------------- The rest is coming soon
