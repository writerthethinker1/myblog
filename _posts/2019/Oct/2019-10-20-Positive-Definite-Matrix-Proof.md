---
layout: post
title: "Positive Definite Matrix Proof"
category: proofs
tags: thoughts
date: "2019-10-20"
author: Ramneek Narayan
---


This post might not be unique (i.e. the proof already exists), but it wasn't the usual one used when I was learning multivariate statistics. I couldn't find it online (at least easily), so I'm posting it here for others in case they are stuck. Onwards! Order up! ^^

We will prove that if $A$ is a symmetric matrix and invertible that $A$ is positive definite if and only if all of its eigenvectors are strictly positive.

We will prove this in two sections:

Forward direction ($\Rightarrow$):

Suppose $A$ has positive eigenvalues, then by definition $\lambda_i > 0$ for all $i \in \lbrace 1,...,n\rbrace$. Since $A$ is symmetric, it has a spectral decomposition and all of its eigenvectors are mutally orthogonal. Further, these eigenvectors form a basis for $\mathbb{R}^n$. Thus, any vector $\vec{x} \in \mathbb{R}^n$ can be represented as a linear combination of eigenvectors or $\vec{x} = \alpha_1\vec{v}_1 + \dots + \alpha_n \vec{v}_n$ for all $\alpha_i \in \mathbb{R}$ and $\vec{v}_i \in \mathbb{R}^n$. Now the product $\vec{x}^TA\vec{x}$ can be expressed as:

$$
\begin{equation}\vec{x}^TA\vec{x} = \left(\sum_{i = 1}^{n}\alpha_i\vec{v}_i^T\right)A\left(\sum_{i = 1}^{n} \alpha_i\vec{v}_i\right)\end{equation}
$$

$$\begin{equation}= \left(\sum_{i = 1}^{n}\alpha_i\vec{v}_i^T\right) \left(\sum_{i = 1}^{n} \alpha_i \lambda_i \vec{v}_i\right)\end{equation}$$

$$\begin{equation}= \sum_{i = 1}^{n}\sum_{j = 1}^{n} \alpha_i \alpha_j \lambda_i\vec{v}_i^T\vec{v}_j\end{equation}$$

And by the orthogonality of the eigenvectors this sum turns into:


 $$\begin{equation}\sum_{i = 1}^{n} \alpha_i^2 \lambda_i\vec{v}_i^T\vec{v}_i = \sum_{i = 1}^{n} \alpha_i^2 \lambda_i ||\vec{v}_i||_2^2\end{equation}$$


 and since each term in the sum is positive as each value of the products are positive, we have that $\vec{x}^T A \vec{x} > 0$, as desired.

Backward direction ($\Leftarrow$):

Suppose that $A$ is positive definite, then by definition $\vec{x}^TA\vec{x} > 0$ for any $\vec{x} \in \mathbb{R}^n$. Now, consider the product $\vec{x}^T A \vec{x}$ in terms of eigenvectors, the end result is:


 $$\begin{equation}\sum_{i = 1}^{n} \alpha_i^2 \lambda_i \vec{v}_i^T\vec{v}_i\end{equation}$$

 which can be rearranged to:

$$\begin{equation}\sum_{i = 1}^{n} \alpha_i \vec{v}_i^T(\alpha_i\lambda_i\vec{v}_i) = \sum_{i = 1}^{n}\left(\alpha_i\vec{v}_i\right)^TA(\alpha_i\vec{v}_i)\end{equation}$$

Now, each summand $\left(\alpha_i\vec{v}_i\right)^TA(\alpha_i\vec{v}_i)$ is greater than 0 since the vectors $\alpha_i \vec{v}_i$ and $A (\alpha_i \vec{v}_i)$ are parallel. In the lefthand side of the above equation, each of the elements of the summand except $\lambda_i$ are known to be positive (since $\alpha_i^2 > 0$ and $\|\| \vec{v}_i \|\|^2 > 0$). But, since the whole summand is positive, it must be the case that $\lambda_i > 0$ for all $i \in \{1,...,n\}$, as desired.

Since both sides of the bi-implication have been proven, we may conclude that symmetric invertible matricies are positive semi-definite if and only if their eigenvalues are positive. This concludes the proof. Q.E.D. <i class="fas fa-meteor"></i>
