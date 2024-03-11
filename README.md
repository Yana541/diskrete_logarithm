# Definition
 ## Discrete Logarithm

The discrete logarithm problem involves solving the equation:
![изображение](https://github.com/Yana541/diskrete_logarithm/assets/149325426/d462a8ec-8edc-4045-8072-876ec90e0fec)


where `a ` and ` m` are coprime (note: if they are not coprime, the algorithm described below is incorrect; although, presumably, it can be modified to still work).

Here is the algorithm known as the "baby-step-giant-step algorithm," proposed by Shanks in 1971, which runs in ![изображение](https://github.com/Yana541/diskrete_logarithm/assets/149325426/b21ee136-3539-48e5-9046-84f2bfd61134)

 time. This algorithm is often simply referred to as the "meet-in-the-middle" algorithm (because it is one of the classical applications of the "meet-in-the-middle" technique: "dividing the task in half").

### Algorithm

So, we have the equation:

![изображение](https://github.com/Yana541/diskrete_logarithm/assets/149325426/2a104f17-e110-40a1-924f-1c0a777a5cc0)


where `a` and `m` are coprime.

Let's transform the equation. Assume:

![изображение](https://github.com/Yana541/diskrete_logarithm/assets/149325426/a30187ef-9bcc-4393-8245-2a6573725b57)


where `n ` is a predetermined constant (how to choose it depending on `m` will be understood later). Sometimes ` p ` is called the "giant step" (because increasing it by one increases ` x` by `n `, while `q `is called the "baby step."

It is obvious that any ` x` (from the interval `([0;m)`) — it's clear that such a range of values will be sufficient) can be represented in this form, and it will be enough for the values:

![изображение](https://github.com/Yana541/diskrete_logarithm/assets/149325426/b1b5010b-11d7-4ae6-affe-6cf80fefc297)


Then the equation takes the form:

![изображение](https://github.com/Yana541/diskrete_logarithm/assets/149325426/5f3b0b49-5162-431f-ac2c-3de8b597159f)


from where, using the fact that `a` and `m` are coprime, we get:

![изображение](https://github.com/Yana541/diskrete_logarithm/assets/149325426/bc3fb9be-aa02-4ece-b80d-a6a68aedd5b3)


To solve the original equation, it is necessary to find the corresponding values of `p` and `q` such that the values of the left and right sides coincide. In other words, it is necessary to solve the equation:

![изображение](https://github.com/Yana541/diskrete_logarithm/assets/149325426/7ffd4bfd-762b-437e-8231-e85728760399)


This problem is solved using the meet-in-the-middle method as follows. The first phase of the algorithm: calculate the values of the function `f_1 ` for all values of the argument `p `, and sort these values. The second phase of the algorithm: iterate over the value of the second variable `q `, calculate the second function `f_2 `, and search for this value among the precomputed values of the first function using binary search.
