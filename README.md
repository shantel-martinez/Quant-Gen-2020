### Quantitative Genomics: CNL BTRY 6830 

Dr. Jason Mezey | Syllabus: [Local file](./Syllabus_2020 QuantGen_V2.pdf) or [Online file](http://mezeylab.cb.bscb.cornell.edu/labmembers/documents/class_materials_2020/2020%20QuantGen_Syllabus_V2.pdf)

### 01: General 

Lecture 01 Slides [Local](./01_MC_LabMeeting_10_16.pdf.pdf) or [Online](http://mezeylab.cb.bscb.cornell.edu/labmembers/documents/class_materials_2020/QG20%20-%20Lecture1-slides_v1.pdf)

All lecture videos are found on Dr. Mezey's Course [webpage](http://mezeylab.cb.bscb.cornell.edu/Classes.aspx). Notes taken here are from the Spring 2020 lecture series.

Lecture 1 was mostly course housekeeping and a general overview of what quantitative genomic is. I will also keep general notes regarding the course and etc in this section.  

Genome: all of the DNA in an individual
Medical Genetics, Agriculture Genetics, Evolutionary Genetics are not bringing genomics and phenotype relationship approaches. 

Quick link: [List of mathematical symbols](https://en.wikibooks.org/wiki/LaTeX/Mathematics#List_of_mathematical_symbols) for markdown note taking

### 02: Probability Basics

Lecture 02 Slides [Local](./02_QG20 - Lecture2-slides_v1.pdf) or [Online](http://mezeylab.cb.bscb.cornell.edu/labmembers/documents/class_materials_2020/QG20%20-%20Lecture2-slides_v1.pdf)

#### Biology Basics

In the very basic general sense: we will use statistical modeling to infer something about biology  
Why measure DNA: the code is the same in every cell; inheritance; we can quantify it ; an organism DNA is almost all the same; it is responsible for construction/maintenance of organisms.  

#### Probability

We cant measure everything that impact height, disease, yield
but we can take repetitive measurements and use probability and statistics to infer the patterns we observe  
Probability (non-technical def) - a mathematical framework for modeling under uncertainty   
Statistics (non-technical def) - a system for interpreting data for the purposes of prediction and decision making given uncertainty  

<img align="right" src="D:\General Research Files\Protocols and Information\Quant Gen Mezey 2020\img\Quant_Gen_2020_Notes\image-20200330174031654.png" alt="image-20200330174031654" style="zoom: 33%;" />  
The System: the genetic contribution to height (the process in which we would like to know something about)

#### Sets / Set Operations / Definitions

**Set** - any collection, group, or conglomerate, often defined with `[]`
**Element** - a member of a set 

Set Operations:  
**Union** $\cup$ $\equiv$ an operator on sets which produces a single set containing all elements
of the sets. *Putting them together; All of the unique elements combined* 
$$
[AB] \cup [BC] = [ABC]
$$

**Intersection** $\cap$ $\equiv$ an operator on sets which produces a single set containing all elements
common to all of the sets.  
$$
[AB] \cap [BC] = [B]
$$
Important Definitions:
**Element of** $\in$ $\equiv$ an object within a set, e.g. *H* $\in$ {*H*, *T*}    
*shorthand notation for example if the set is Heads , Tails , Heads is an element of that set*

**Subset** $\subset$ $\equiv$ a set that is contained within another set, e.g. {*H*} $\subset$ {*H*, *T*}   
*The set Heads is contained within another set Heads, Tails* 

**Complement** $A^c$ $\equiv$ the set containing all other elements of a set other than $A$, e.g. {*H*}$^c =$ {*T*}   
*The total set is Heads, Tails. The complement of Heads is Tails*  

**Disjoint Sets** $\equiv$ sets with no elements in common 

A Special Set:

**Empty Set** $\theta$ $\equiv$  the set with no elements (empty set is unique and is sometimes represented as { } )
$$
[A] \cap [C] = \theta
$$
*Set A, intersection or elements in common with Set C is no elements in common, so it is an empty set, theta* 

**Sample Space** $\Omega$ - set comprising all possible outcomes associated with an experiment, Examples:  
-- (Experiment / Sample Space): 
-- “Single coin flip” / {H, T}
-- “Two coin flips” / {HH, HT, TH, TT} 

*this will apply when we talk about alleles* 

**Events** - a subset of the sample space, Examples:  
(Sample Space / Examples of Events):
-- “Single coin flip” / $\theta$ , {H}, {H, T}  *note every set you get will contain an empty set $\theta $* 
-- “Two coin flips” / {TH}, {HH, TH}, {HT, TH, TT}

**Probability Function** has to be able to assign a number defining "chance", probability, for each event. Not just the elements H or T, but every event:  $\theta$ , {H}, {T}, {H, T} 

**Sigma Algebra/Sigma Field** $F$ a collection of events (subset) of $\Omega$ of interest with the following three properties  (formal definition)

1. $\theta \in F$  i.e., an empty set is an object or element within the Sigma Algebra
2. $A \in F$ then $A^c \in F$   i.e., set A (or any event we care about) is included within the Sigma Algebra then the complement of A is included Sigma Algebra
3. $A_1,  A_2 ,... \in F$ then $\bigcup_{i=1}^{\infty} A_i \in F$  The union (a set combining the unique elements of individual sets) of a bunch of disjoint sets are also included in the Sigma Algebra

The Sigma Algebra is a list of every event. 

The sample space of single coin flip is heads, tails. The Sigma Algebra is: empty set, Heads, Tails, Heads Tails  {H,T} / $\theta$ , {H}, {T}, {H, T} 

### 03: Probability, conditional probability

Lecture 03 Slides [Local](./03_QG20 - Lecture3-slides_v1.pdf) or [Online](http://mezeylab.cb.bscb.cornell.edu/labmembers/documents/class_materials_2020/QG20%20-%20Lecture3-slides_v1.pdf)

*con't from lecture 2:*

If me move over the the two-coin flip example {HH,HT,TH,TT}, why would we need to define ALL of the events? Lets look at one set: {HH,HT} which is the event where Heads is flipped first. This is important information if you want to look at all the events where Heads comes first. So defining that probability matters. 

For the Reals (numbers) for the Sigma Algebra, we cant use all subsets. A problem that can occur is we have more sets than "we need": called non-measurable sets. 

[a,b] means when using brackets [] means "include"; so the entire interval between a,b  and a,b are included

[a,b) doesn't include b (a,b] doesn't include a (a,b) doesn't include a or b

When dealing with the Reals, we will be using intervals and map in intervals. difficult concept to grasp why, take more math courses, analysis hahahah

#### Probability Functions 

The probability function maps a sigma algebra of a sample to a subset or the Reals:

$Pr(F) : F \to [0,1]$

> Pr(F) just means that a function that takes things/sets in the Sigma Algebra (F) in , gives us an output. And the arrow maps it to the output we are mapping it to. This is the subset of the Reals we are mapping to between/including 0,1

Axioms (property assumed true; we are going to assume that these are true) of Probability:

1. For $A \subset \Omega , Pr(A) \geq 0$  

   > for any event (A) as a subset within a sample space, the probability of any event is greater than or equal to 0

2. $Pr(\Omega) = 1$   

   > the probability of all of the possible outcomes (the sample space) is equal to 1

3. For $A_1,A_2, ... \in \Omega $  if $A_i \cap A_j = \theta$ (disjoint) for each $i \neq j:Pr(\bigcup_{i}^{\infty} A_i )= \sum_i^\infty Pr(A)$   

   > for any subset/events (sets A1, A2, and so on) that are objects in the sample space, if the commonality of Ai and Aj is equal to an empty set (no common elements) they are disjointed, for each i not equal to j, then the probability of the union from i to infinity of set Ai is equal to the sum from i to infinity of the Probability of A. 
   >
   > i.e. if any two subsets/events are disjoint, the probability of the union of them is equal to the sum of their probabilities. 

![image-20200402100013885](D:\General Research Files\Protocols and Information\Quant Gen Mezey 2020\img\Quant_Gen_2020_Notes\image-20200402100013885.png)

This makes sense. 

To think through the 3rd axiom: $Pr(HH \cup HT) = Pr(HH) + Pr(HT) = 0.25+0.25 = 0.5$ 

The probability functions we are going to deal with when we use Reals are different because we can now use intervals than points. 

#### Conditional Probability 

I hear a weather report, my probability model I know something is happen, what do I think now is going to happen, given that. 

> we could consider the conditional probability that someone will be taller or shorter if they have a “T” at a particular position in the genome

The way we write conditional probability:   

$P(A_i|A_j) = \frac{Pr(A_i\cap A_j)}{Pr(A_j)} $

>  Probability of an event Ai given that we've observed Aj is equal to the Prob of Ai and Aj divided by the Prob of Aj

**Pause** lets tie some previous concepts together as an example to help explain conditional probability 

We have a probability model: $Pr\{HH\} = Pr\{HT\} = Pr\{TH\} = Pr\{TT\} = 0.25$

Then lets map out possibilities (**A**), looks sorta like a punnet square, ay:

**A)** <img src="D:\General Research Files\Protocols and Information\Quant Gen Mezey 2020\img\Quant_Gen_2020_Notes\image-20200402114440591.png" alt="image-20200402114440591" style="zoom: 40%;" />   **B)**<img src="D:\General Research Files\Protocols and Information\Quant Gen Mezey 2020\img\Quant_Gen_2020_Notes\image-20200402114647888.png" alt="image-20200402114647888" style="zoom:40%;" />

**Figure 1** - **A**) the possibility of structured similarly to a punnet square. **B**) the probability for each outcome. 

Now use the same punnet square, but include the probabilities for each outcome. Notice the end of row 1 is the probability that $H_{1st}$ will come first in our two coin flip scenario. Which means the $Pr(H_{1st}) = Pr(HH \cup HT)$ and as we've learned about the third axiom above, the $ Pr(HH \cup HT) = Pr(HH) + Pr(HT) = 0.25 + 0.25 = 0.5$ 

So what is the probability we see heads second given that I've observed heads 1st. 

$Pr(H_{2nd}|H_{1st})$ and we need information about the probability heads is first, top row $Pr(H_{1st})$ . Then we care about the probability where heads comes 1st and 2nd: $Pr(H_{1st} \cap H_{2nd})$ 

**Bringing all the concepts together** : looking at conditional probability: 

$P(H_{2nd}|H_{1st}) = \frac{Pr(H_{2nd} \cap H_{1st})}{Pr(H_{1st})} =\frac{Pr(HH)}{Pr(HH \cup HT)}  = \frac{0.25}{0.25+0.25} = 0.5$

because we need to make sure our probability model satisfies all axioms. 

### 04: Independence, Random

Lecture 04 Slides [Local](./04_QG20 - Lecture4-slides_v2.pdf) or [Online](http://mezeylab.cb.bscb.cornell.edu/labmembers/documents/class_materials_2020/QG20%20-%20Lecture4-slides_v2.pdf)

#### Independence

if an event happens, it doesn't influence another event from happening. Example: it will snows in Ithaca, and Serena Williams will play at Wimbledon. Those events are independent of one another. 

Se we define independence as:

$Pr(A_i|A_j) = Pr(A_i)$           [**1**]

> If Ai is independent of Aj, then the conditional probability Ai given Aj is just equal to the probability of Ai. Knowing Aj happened does not change what happened to Ai. this makes sense.

However, people always show independence as: 

$Pr(A_i \cap A_j) = Pr(A_i)Pr(A_j)$      [**2**]

> Two events are independent, the probability of Ai intersection Aj is the probability of Ai times the probability of Aj

How do we get from the concept from equation [**1**] to the traditional equation [**2**]. 

lets start with: $Pr(A_i|A_j) = Pr(A_i)$  

and we know our conditional probability: $P(A_i|A_j) = \frac{Pr(A_i\cap A_j)}{Pr(A_j)} $

and the only way for this equation  to $ = Pr(A_i)$ is it the numerator cancels out the Aj and includes Ai. 

where Aj cancels out, makes equation [**1**] true : $P(A_i|A_j) = \frac{Pr(A_i\cap A_j)}{Pr(A_j)} = \frac{Pr(A_i) Pr(A_j)}{Pr(A_j)} = Pr(A_i)$ 

therefore, for this to work, $Pr(A_i \cap A_j) = Pr(A_i)Pr(A_j)$ , which we see from both numerators.

##### Example of Independence

Lets revert back to Figure 1 for our two coin flip example. Below fills in the probabilities for this example:

<img src="D:\General Research Files\Protocols and Information\Quant Gen Mezey 2020\img\Quant_Gen_2020_Notes\image-20200402131008979.png" alt="image-20200402131008979" style="zoom:50%;" />

In this model, $H_{1st}$ and $H_{2nd}$ are independent. Why? 

The probability of $Pr(H_{1st}) = 0.5$ , and the probability of $Pr(H_{2nd}) = 0.5$ 

Using out equation of independence: $Pr(A_i \cap A_j) = Pr(A_i)Pr(A_j)$

$Pr(H_{1st} \cap H_{2nd}) = 0.25$  **and**  $Pr(H_{1st})Pr(H_{2nd}) = 0.5 \times 0.5 = 0.25$

0.25 = 0.25, therefore  $H_{1st}$ and $H_{2nd}$ are independent. 

##### Example of Non-Independence

Now if our probabilities change to the following values:  *Note, this example still follows all three axioms, it is still a probability measure*

<img src="D:\General Research Files\Protocols and Information\Quant Gen Mezey 2020\img\Quant_Gen_2020_Notes\image-20200402131723091.png" alt="image-20200402131723091" style="zoom:50%;" />

The probability of $Pr(H_{1st}) = 0.5$ , and the probability of $Pr(H_{2nd}) = 0.5$ 

$Pr(H_{1st} \cap H_{2nd}) = 0.4$  **and**  $Pr(H_{1st})Pr(H_{2nd}) = 0.5 \times 0.5 = 0.25$

Since independence is defined as: $Pr(A_i \cap A_j) = Pr(A_i)Pr(A_j)$

$0.4 \neq 0.25$, therefore  $H_{1st}$ and $H_{2nd}$ are non-independent. 

#### Random Variables

A random variable is a real valued function on the sample space. It is a function that maps to the Reals. Remember, a function takes an input, gives you an output.  So we take things from out sample space $\Omega$ , inputs those into a function (box), and we get an output of Reals numbers. 

Lets walk through an example to better understand a random variable. 

If our sample space, $\Omega = \{HH, HT, TH, TT\} $   
What we want to know is the number of Tails in two flips. Can we define a function that takes two sets and maps to a number of tails in two flips? Easily. Lets look at each set individually:

> *But first, lets note that function for a random variable is no longer $F$ , it $X$* 

$X(HH) = 0$ The function of HH has a value of 0, there are no Tails

$X(HT) = 1$ The function of HT has a value of 1, there is one Tail

and so on: $X(TH) = 1, X(TT) = 2$ 

Now remember probability model: $Pr\{HH\} = Pr\{HT\} = Pr\{TH\} = Pr\{TT\} = 0.25$

if the $Pr\{HH\} = 0.25$ and $X(HH) = 0$ the probability that $Pr(X = 0) = 0.25$ 

if the $Pr\{HT\} = Pr\{TH\} = 0.25$ and $X(HT) = 1$ and $X(TT) = 1$ the probability that $Pr(X = 1) = 0.25 + 0.25 = 0.5$ 

if the $Pr\{TT\} = 0.25$ and $X(TT) = 2$ the probability that $Pr(X = 2) = 0.25$ 

**Crucial Point:**  Because we've defined a probability function for our Sigma Algebra, once we've defined a random variable on our sample space, we've **induced** a probability function on our random variable. 

To bridge probability of an occurrence and what actually occurs in the experiment $e$ often use an “upper” case letter to represent the function ($X$) and a “lower” case letter to represent the values ($x$) we actually observe: $Pr(X = x)$ 

our downstream discussion will be divided two ways: looking at **discrete** (taking individual point values) or **continuous** (taking on values within an interval of the reals) values

Lets depict our concepts now with $x$ as what we observed in the trial. We've linked the experiment, $\Omega$, $F$, and the probability measure on our Sigma Algebra $Pr(F)$. 

<img src="D:\General Research Files\Protocols and Information\Quant Gen Mezey 2020\img\Quant_Gen_2020_Notes\image-20200402140236672.png" alt="image-20200402140236672" style="zoom: 33%;" />

Now we add in $X$ which is our Random Variable, which is a function on the sample space. But it also **induces** the probability function on the Sigma algebra and allow the random variable to equal our outcome (abstract model bridged to our observations). 

<img src="D:\General Research Files\Protocols and Information\Quant Gen Mezey 2020\img\Quant_Gen_2020_Notes\image-20200402140558656.png" alt="image-20200402140558656" style="zoom: 33%;" />

##### Discrete R.V. 

Using the same example of number of Tails observed: 
$X(HH) = 0, X(HT) = 1, X(TH) = 1, X(TT) = 2$ 

These map to the natural numbers, and we can handle these different than the reals (like $\infty$). 

The probability model (again): $Pr\{HH\} = Pr\{HT\} = Pr\{TH\} = Pr\{TT\} = 0.25$

Using what we calculated above, $Pr(X = 0) = 0.25$ , $Pr(X = 1) = 0.5$, and $Pr(X = 2) = 0.25$ can be also written as:

$P_X(x) = Pr(X = x) = \begin{cases}  Pr(X = 0) = 0.25 \\ Pr(X = 1) = 0.5 \\ Pr(X = 2) = 0.25  \end{cases} $   [**3**]<img align = "right" src="D:\General Research Files\Protocols and Information\Quant Gen Mezey 2020\img\Quant_Gen_2020_Notes\image-20200402144017858.png" alt="image-20200402144017858" style="zoom: 50%;" />

> $P_X(x)$ is the probability of different values $(x)$ for the random variable $X$ 

we call this a **probability mass function**  (pmf), is a probability distribution (as you can sort of see in the graph), but for discrete values we use the term pmf. 

##### Continuous R.V.

The **cumulative mass function** $F_X(x) = Pr(X \leq x)$ 

Using our two-coin flip example, lets try $x=-1$, and we look at the equation I want $Pr(X \leq-1)$ ... From $-\infty$ to $-1$ what is all that probability? Well referring back to equation [3], the probability would be 0. 

$Pr(X \leq0) = 0.25$ , then $Pr(X \leq1) = 0.5$, and $Pr(X \leq2) - 0.25$ 

as you would graph that, anything below $x = 0$, the $F_X(x \leq 0) = 0$ ..making a straight line to $-\infty$ . (bottom line in graph). <img align = "right" src="D:\General Research Files\Protocols and Information\Quant Gen Mezey 2020\img\Quant_Gen_2020_Notes\image-20200402143644817.png" alt="image-20200402143644817" style="zoom:50%;" />

Then when we get to $F_X(x = 0) = 0.25$, it jumps up to 0.25. 

However there is no probability defined between 0 and 1, so a continuous (?) value is used. 

Then when we get to $F_X(x = 1) = 0.5$, it jumps up to 0.5, and so on.

 A **probability density (*calculating*) functions** (pdf) defines the probability of an interval of a random variable, i.e. the probability that the random variable will take a value in that interval:

$Pr(a \leq X \leq b) = \int_a^b f_X (x)dx $  [**4**]

>  adding up all of the area under the curve. So this area under the curve is the probability of this interval. 

We use this function to calculate the probability of intervals, and we do this by integrating this function 

**Critical Point**: Don't think of the pdf as a function that directly connects to the probability (like the cum. mass func does or the probability mass func.), we have to integrate it, to find the probability. 

So what does the probability of an interval even mean? It just means its the probability of **any** of the events from a to b, i.e. -1.5 to 0.5. It includes the probability of -1, -0.8, all of them. 

#### 05: Vectors, Expectations, and Variances

Lecture 05 Slides: [Local](./05_QG20 - Lecture4-slides_v1.pdf) or [Online](http://mezeylab.cb.bscb.cornell.edu/labmembers/documents/class_materials_2020/QG20%20-%20Lecture5-slides_v1.pdf)

*con't from 04 lecture on Random Variables*

dont worry if you see this equation and it freaks you out, many of you have not. "Just remember, an equation is a set of instructions. If it is explained appropriate to you, you will understand how to use it"

$ f_X(x) = \frac{1}{\sqrt{2\pi\sigma^2}} e^{- \frac{(x-\mu)^2}{2\sigma^2}} $  <img align ="right" src="D:\General Research Files\Protocols and Information\Quant Gen Mezey 2020\img\Quant_Gen_2020_Notes\image-20200402155243409.png" alt="image-20200402155243409" style="zoom:50%;" />

what is $\mu$ doing in the equation? re-centering. If $\mu = 0$  you will get a function centered at 0. 

what is $\sigma^2$ showing you? the spread of the function. 

This graph is just depicting different $\mu$'s and $\sigma^2$'s 

> we will return to this later in the course.

##### Random Vectors  

We will use vectors to keep track of things, like random variables in a vector. Why? 

Lets define not one, but two random variables. Our first ($X_1$) we've seen before, random variables defining the number of Tails that are observed. But lets also add $X_2$ which is when heads is observed first. 

$X_1 = \begin{cases}  X_1(HH) = 0 \\ X_1(HT) = X_1(TH) = 1 \\ X_1(TT) = 2  \end{cases} $         $X_2 = \begin{cases}  X_2(TH) = X_2(TT) = 0 \\ X_2(HH) = X_1(HT) = 1 \end{cases} $

The probability function induces the following pmf for the random vector **X** = [X1, X2], where we use bold **X** do indicate a vector (or matrix). Again, the probability function of the random vector is **X**.  

> bold usually indicated that that is a vector, it is more than just one element.

Lets write the pmf for **X** in four different ways:

$Pr(\textbf{X}) = Pr(X_1 = x_1, X_2 = x_2) = P_X (x) = P_{X_1,X_2}(x_1, x_2)$

> all of these ways of writing out the probability of the random vector, mean the same thing

Calculating the probability, there are six outcomes because $X_1$ has 3 outcomes and $X_2$ has 2 outcomes, and 3x2 is 6 potential outcomes. 

> notice there are some probabilities = 0. Why, because if you look closely at those probabilities, like HH, there will never be a T in HH so the probability to get a T in HH = 0



#####  Expectations





#####  Variances



