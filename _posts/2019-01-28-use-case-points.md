---
layout: post
title: "Use Case Points."
categories: [Software engineering]
tags: [software estimation, use case points]
comments: true
---

### Use Case Points (UCP)

* ####  Unadjusted Use Case Weight (UUCW)

![Unadjusted Use Case Weight](https://raw.githubusercontent.com/qndev/blog/gh-pages/images/posts/uucw.png)

* #### Unadjusted Actor Weight (UAW)

<!--more-->

![Unadjusted Actor Weight](https://raw.githubusercontent.com/qndev/blog/gh-pages/images/posts/uaw.png)

* #### Technical Complexity Factor (TCF)

  #### TCF = 0.6 + (TF/100)

![Technical Complexity Factor](https://raw.githubusercontent.com/qndev/blog/gh-pages/images/posts/tcftable.png)

* #### Environmental Complexity Factor (ECF)

  #### ECF = 1.4 + (-0.03 x EF)

![Environmental Complexity Factor](https://raw.githubusercontent.com/qndev/blog/gh-pages/images/posts/ecftable.png)

  * #### Corresponding interpolation values (S) of Environmental Complexity Factor (ECF)

![Corresponding interpolation values (S) of Environmental Complexity Factor](https://raw.githubusercontent.com/qndev/blog/gh-pages/images/posts/ecftable2.png)

  * #### Experience Stability Estimate (ES)

  $$ES = \sum_{i=1}^8 S_i$$

![Environmental Complexity Factor](https://raw.githubusercontent.com/qndev/blog/gh-pages/images/posts/es.png)

* #### Unadjusted Use Case Weight (UUCW)

  #### UUCW = (Total No. of Simple Use Cases x 5) + (Total No. Average Use Cases x 10) + (Total No. Complex Use Cases x 15)

* #### Unadjusted Actor Weight (UAW)

  #### UAW = (Total No. of Simple Actors x 1) + (Total No. Average Actors x 2) + (Total No. Complex Actors x 3)

* #### Use Case Points (UCP)

  #### UCP = (UUCW + UAW) x TCF x ECF

* #### Estimate Effort (EE)

  #### EE = AUCPxP (Hours)

* #### Step by step Use Case Points Methods

![Use Case Points Methods](https://raw.githubusercontent.com/qndev/blog/gh-pages/images/posts/UseCasePointsMethod.png)

* #### Review App Demo

  * #### Create New Project

![Create New Project](https://raw.githubusercontent.com/qndev/blog/gh-pages/images/posts/project.png)

  * #### Use Case & Actor

![Use Case & Actor](https://raw.githubusercontent.com/qndev/blog/gh-pages/images/posts/usecase.png)

  * #### Technical Complexity Factor

![Technical Complexity Factor](https://raw.githubusercontent.com/qndev/blog/gh-pages/images/posts/tcf.png)

  * #### Environmental Complexity Factor

![Environmental Complexity Factor](https://raw.githubusercontent.com/qndev/qndev.github.io/master/public/images/ecf.png)

  * #### Estimate Effort

![Estimate Effort](https://raw.githubusercontent.com/qndev/blog/gh-pages/images/posts/effort.png)

* #### Source code

  [Use Case Points](https://github.com/qnDev/ktcnpm.20181/tree/master/UseCasePoint)

* #### References

  [1] [Use Case Points From Wikipedia](https://en.wikipedia.org/wiki/Use_Case_Points)

  [2] [Software cost estimation using use case points: Getting use case transactions straight](https://www.ibm.com/developerworks/rational/library/edge/09/mar09/collaris_dekker/index.html)

  [3] [UML - Use Case Diagrams](https://www.tutorialspoint.com/uml/uml_use_case_diagram.htm)

---
