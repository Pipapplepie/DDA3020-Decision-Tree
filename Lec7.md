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

By scaling the numerator, (How?) we could simplify the problem to: **(P)**

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

## Lagrange Duality and KKT conditions (Review)

<img src='https://user-images.githubusercontent.com/107236740/228141484-4a611470-b65e-4691-84c6-87a13254c91a.png' width=700>

## Optimization of SVM by Lagrange Duality

We can modify the original probelm **(P)** to its Lagrangian problem:

<img src='https://user-images.githubusercontent.com/107236740/228143908-da99c85d-ebeb-455c-911b-154667efbe8e.png' width = 700>

Solved for $\alpha$, so we get $w = \sum_i^m \alpha_i y_i x_i$.

If $\alpha_i = 0$, then it means $x_i$ does not contribute to w. Otherwise, $\alpha_i > 0$, $x_i$'s are called **support vectors**, which locate at the hyperplanes $y_i f_{w,b}(x_i) = 1$. We therefore define the support set S = $\{ i | \alpha_i > 0 \}$. This is why we call it **support vector machine**!

To determine th bias parameter b:

<img src='https://user-images.githubusercontent.com/107236740/228146597-05a8ab50-a1ba-4b0b-a376-f598b06a15aa.png' width=700>

## SVM with slack variables (Soft Margin SVM)

* **Hard margin SVM**: the set is guaranteed linearly separable. However, in most cases, the set is **non-separable**.

<img src='https://user-images.githubusercontent.com/107236740/228150831-adfc5dd8-dd23-4986-9701-81a6af776ccb.png' width=600>

Thus, our feasible condition changes from $$y_i f_{w,b}(x_i) \geq 1 \ \forall i$$ to $$y_i f_{w,b}(x_i) \geq 1 - \epsilon_i \ \forall i$$

Now, we can construct new Lagrangian problem:

<img src='https://user-images.githubusercontent.com/107236740/228153058-a11ce363-73db-49ef-bc35-7d9dd41fd005.png' width=700>

In the end, we can simplify the problem to:

<img scr='https://user-images.githubusercontent.com/107236740/228154375-fd5d8ef7-ba17-4c23-bee2-86191635dd80.png' width=700>


