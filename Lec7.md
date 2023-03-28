# Support Vector Machine (SVM)

## Motivition: Binary Classification

$y_i \in \{ -1, 1 \}$. logistic regression gives multiple solutions to perfectly fit the training data. Now we want one decision boundary that can make the **largest margin**.

<img src='https://user-images.githubusercontent.com/107236740/228124852-d02b1bf2-cc86-4745-8e92-522e34cfd9b6.png' width=500>

This **large margin classifier** is also called support vector machine. (SVM)

## Derivation

_review_: inner product of vectors, orthogonal direction, projection to the hyperplane:

If given the hyperplane: $f_w(x) = w^Tx = 0$ then the projection of x is $\frac{|f_w(x)|}{|w|}$.

$f_{w,b}(x) = w^Tx + b = 0$ then the projection of x is $\frac{|f_{w,b}(x)|}{|w|}$.

So we derive the margin over all training data: $$min_i \ \frac{|f_{w,b}(x_i)|}{|w|}$$

or just $min_i \ \frac{y_i f_{w,b}(x_i)}{|w|}$ since $y_i$ = 1 or -1.

Thus, we want to solve the optimization problem:
$$max_{w,b} \ min_i \ \frac{y_i f_{w,b}(x_i)}{|w|}$$

By scaling the numerator, (How?) we could simplify the problem to:

$$min_{w,b} \ \frac{1}{2} ||w||^2 $$

subject to $$y_i f_{w,b}(x_i) \geq 1 \ \forall i$$

By solving the problem above, we can predict test data $x_t$ by the sign using $w*$ and $b*$.

## Alternative Derivation: Hinge Loss

<img src='https://user-images.githubusercontent.com/107236740/228136892-94431e65-f48b-446b-afad-6dd67c92f8b2.png' width=700>

So the hinge loss is $$max(0, y_i f_{w,b}(x_i))$$

which is non-smooth. 

We can simplify the objective function to:

$$min_{w,b} \ \frac{1}{2} ||w||^2$$

subject to $$w^Tx_i + b \geq 1, \ if \ y_i=1; \ $w^Tx_i + b < 1, \ if \ y_i=-1.$$

Same as above derivation.

Actually, when the projection length is larger, it gives smaller ||w||, which is exactly what we want.

## Lagrange Duality and KKT conditions
