# Differentiation

In this segment, let's revisit some concepts and formulae of derivatives.

## **Differentiation**

Differentiation is the action of computing a derivative. The derivative of a function $y=f(x)$ is a measure of the rate at which the value $y$ of the function changes with respect to the change in the variable $x$. It is called the derivative of f with respect to x.
Although in practice, we usually compute derivatives using 'rules' $(\text{such as} \dfrac{\delta(x^2)}{\delta\\x})$ it is worth recalling how these rules are arrived at, and more importantly, what they mean.

## Video

To get a basic understanding of derivatives, watch this video on the [first principles of derivatives](https://www.youtube.com/watch?v=ay8838UZ4nM&index=18&list=PL19E79A0638C8D449) by Khan Academy.

To get a visual understanding of limits, you can **optionally** [watch this video on limits](https://www.youtube.com/watch?v=kfF40MiS7zA&list=PLZHQObOWTQDMsr9K-rj53DwVRMYO3t5Yr&index=7) by 3Blue1Brown. We have summarized the concepts from these two videos in the section below. 
$$\large{m=\dfrac{\text{change in }y}{\text{change in }x}=\dfrac{\Delta\\y}{\Delta\\x}}$$
$$\large{m=\dfrac{\Delta\\f(a)}{\Delta\\a}=\dfrac{f(a+h)-f(a)}{(a+h)-(a)}=\dfrac{f(a+h)-f(a)}{h}}$$
$$\large{f'(a)=\lim\limits_{h\to\\0}\dfrac{f(a+h)-f(a)}{h}}$$
 Let's consider an example f(x)=x2 and calculate it's derivative at x=4: 
 $$\large{f'(4)=\lim\limits_{h\to\\0}\dfrac{f(4+h)-f(4)}{h}}$$
 $$\large{=\lim\limits_{h\to\\0}\dfrac{16+8h+h^2-16}{h}=\lim\limits_{h\to\\0}\dfrac{8h+h^2}{h}=\lim\limits_{h\to\\0}(8+h)}$$
 $$\large{=\lim\limits_{h\to\\0}(8+h)}=8+0=8$$
 The above method is also referred to as **derivatives by first principles**. This method is the foundation for the rest of differential calculus: every differentiation rule and identity in calculus is based on the concept of derivatives by first principles.

#### Derivatives by First Principles

Qn: Differentiate the following function f(x)=x3+x2/2+3 and evaluate the differential at x=5. You may already know how to compute the derivative directly, but you may try doing it using first principles for a short algebra warm-up.  

- 80

- 70

- 75

- 100

Ans: A.

Qn: Differentiate the function f(x)=x2−5x+6 and evaluate the differential at x=−1 using first principles.  

- -7

- 7

- 3

- -3

Ans: A.

In practice, computing derivatives by first principles is a tedious process. But once the derivatives of a few simple functions are known, the derivatives of other complex functions can be easily computed using some rules_._

## **Differentiation Rules for Common Functions**

In the following section, we have summarised the differentiation rules for common functions. You can quickly skim through these.

- **Derivatives of powers:** 
	If $f(x)=x^r$, where r is any real number, then $f'(x)=rx^{r-1}$. For example if $f(x)=x^{1/5}$, then $f'(x)=(1/5)x^{-4/5}$.

- **Exponential and logarithmic functions:**
	$$\large{\dfrac{d}{dx}e^x=e^x}$$
	$$\large{\dfrac{d}{dx}a^x=a^xln(a)}$$
	$$\large{\dfrac{d}{dx}ln(x)=\dfrac{1}{x}$, $x>0}$$
	$$\large{\dfrac{d}{dx}log_a(x)=\dfrac{1}{xln(a)}}$$

- **Trigonometric functions:** 
	$$\large{\dfrac{d}{dx}sin(x)=cos(x)}$$
	$$\large{\dfrac{d}{dx}cos(x)=sin(x)}$$
	$$\large{\dfrac{d}{dx}tan(x)=sec^2(x)=\dfrac{1}{cos^2(x)}=1+tan^2(x)}$$


## Rules for Combined Functions

Here are some rules for combinations of functions: 

- **Constant rule:** If $f(x)$ is constant, then $f'(x)=0$.

- **Sum rule:** $(\alpha\\f+\beta\\g)'=\alpha\\f'+\beta\\g'$, for all $f$ and $g$ and all real numbers $\alpha$ and $\beta$.

- **Product rule:** $(fg)'=f'g+fg'$, for all functions $f$ and $g$.

- **Quotient rule:** $\left(\dfrac{f}{g}\right)'=\dfrac{f'g-fg'}{g^2}$, for all functions $f$ and $g$ where $g\ne0$

- **Chain rule:** if $f(x)=h(g(x))$, then $f'(x)=h'(g(x))*g'(x)*$

## Video

To get a basic understanding of differentiation using the chain rule, watch this video on [Chain rule | Derivative rules](https://www.youtube.com/watch?v=0T0QrHO56qg) by Khan Academy. You can **optionally** watch this video on [Visualizing the chain rule and product](https://www.youtube.com/watch?v=YG15m2VwSjA) [rule](https://www.youtube.com/watch?v=YG15m2VwSjA) by 3Blue1Brown.

The following example illustrates some of these rules in action:
If $\large{f(x)=x^3+sin(x^2)-ln(x)e^x+52}$, then
$$\large{f'(x)=3x^{(3-1)}+\dfrac{d(x^2)}{dx}cos(x^2)-\dfrac{d(ln\ x)}{dx}e^x-ln(x)\dfrac{d(e^x)}{dx}+0}$$
$$=3x^2+2x\ cos(x^2)-\dfrac{1}{x}s^x-ln(x)e^x$$

#### Differentiation

Qn: What is the derivative of the function $f(x)=x^3cos(x)e^x$ ?  

- $f'(x)=-x^3sin(x)+e^xx^3+3e^xx^2cos(x)$

- $f'(x)=-e^xx^3sin(x)+e^xx^3cos(x)+e^xx^2cos(x)$

- $f'(x)=-e^xx^3sin(x)+e^xx^3cos(x)+3e^xx^2cos(x)$

- $f'(x)=-3x^2sin(x)e^x$

Ans: C. *By using the product rule:*
$$\large{\dfrac{d(p(x)*q(x)*r(x))}{dx}=p'(x)q(x)r(x)+p(x)q'(x)r(x)+p(x)q(x)r'(x)}$$
$$\large{=-e^xx^3sin(x)+e^xx^3cos(x)+3e^xx^2cos(x)}$$

#### Differentiation

Qn: What is the derivative of the function f(x)=x3/2+πx2+√49 evaluated at the point x=2 ?

- $f'(2)=\dfrac{2\sqrt{3}}{2}+4\pi+7$

- $f'(2)=\dfrac{3\sqrt{2}}{2}+4\pi$

- $f'(2)=\dfrac{3}{2}+4\pi+7$

- $f'(2)=\dfrac{\sqrt{3}}{2}+4\pi+7$

Ans: B. 
$$\large{f(x)=x^{3/2}+\pi\\x^2+\sqrt{49}}$$
$$\large{f'(x)=\dfrac{3}{2}x^{1/2}+2\pi\\x}$$

Qn: What is the derivative of the function $f(x)=sin(x)e^{cos(x)}$ at the point $x=\pi$?  

- $f'(\pi)=\dfrac{1}{e^2}$

- $f'(\pi)=\dfrac{1}{e^{-2}}$

- $f'(\pi)=\dfrac{1}{e}$

- $f'(\pi)=-\dfrac{1}{e}$

Ans: D.
