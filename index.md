<div style="text-align:center;font-size:30px">﷽</div>









<div style="text-align:center;font-size:48px">Introduction to Recommender Systems</div>







Written by **Mehdi CHEBBAH** & **Yacine ZIDELMAL**.

---

![](assets/Recommender Systems.png)

[TOC]

---

# Introduction

The purpose of this article is to provide a brief overview of the field of recommender systems. We will discuss the history of these systems, the terminology used and their overall classifications.

Intuitively, a Recommendation System, for example for books, can be compared to a library agent who we ask to suggest books to us after having expressed our needs. Indeed, the librarian with his great knowledge of the books in this library compared to a simple user and considering his long experience and the opinions of users, he can provide valuable recommendations which can save a lot of research effort and time. Of course, the user must provide him with sufficient data. This example illustrates a human recommendation, to get closer to technical terms we could say that, the virtual librarian must have three types of information: representations of books in the library (item profiles), representation of users (profiles users), and the algorithms that interfere between the two to produce the recommendations (Amine Naak 2009).

Formally. “*A Recommender System is any system that produces personalized recommendations as output or has the effect of guiding the user in a personalized way to interesting or useful objects in a large space of possible objects*” (Aravind 2018). In other words, a Recommendation System could be considered as a tool, for which a user discloses his profile (represented, in general, by his preferences and tastes), the system in return provides a personalized and reduced image of information sought from the database. If all these information are sent directly back to the client, they will exceed his cognitive abilities.

At first glance, it seems that recommender systems perform the same function as search engines. In fact, we could think of search engines as simple recommender systems that take as input the keywords/tags and provide a subset of the set of items. But the main difference is that the result of search engines is not personalized according to the user's profile, while the result of a Recommender System should depend on it. This means that the same query for a simple search engine will return the same items for all users of the system. On the other hand, the same query in a Recommender System will return different results depending on the user's profile. Another difference is that the application domain of Recommender Systems is wider than that of Search Engines, because Search Engines deal mainly with HTML pages (text), while Recommender Systems are used with all sorts of data, e.g. music (audio), movies (video), HTML pages (text), e-commerce products (complex types), etc.

The first Recommender Systems are reduced to collaborative filtering systems (which will be explained in the next section). They appeared in the early 1990s, when they were recognized as an independent research field. We cite as examples the **Tapestry** (Goldberg et al. 1992) and **GroupLens** (Resnick et al. 1994) systems.

The roots of recommender systems can be traced back to extensive work in cognitive science, approximation theory, information retrieval, and prospective theory, and also have links to management science and marketing in modeling consumer choice (Amine Naak 2009).

We have previously mentioned some terms that are used extensively in this field of research and that need to be defined before we begin, such as: 

- **Item profile**: This is the internal representation of the object we want to recommend (e.g. a product, a movie, an article, music, etc.)
 - **User profile**: This is the internal representation of the user's preferences and historical actions.
 - **Recommended list**: This is the result of the recommendation process and contains a list of items that the system deems relevant for the user.

# Classification of recommender systems

If we analyze the current research direction on recommender systems, we can see that there are mainly three general categories: content-based systems, collaborative filtering-based systems, and hybrid systems [(Mu 2018), (Kuanr et al. 2021)]. These approaches are not dependent on the application domain of the system, they are basic methods that could simply be implemented and deployed and work for any type of data.

In the next section, we will use the example of a movie recommender system to understand the intuition behind these three approaches (i.e., we have a database containing users and movies and the goal is to provide users with movies that might interest them).

## Content Based Recommender Systems

If our movie recommender system is implemented using the content-based approach, this means that if the user watches/likes a specific content the most (say the user watches war movies most of the time), the recommended list will contain that content.

Content-based recommender systems use the content of items and find the similarities between them. After analyzing a suﬀcient number of items that a user has already shown preference for, the user's profile of interests is established. The recommender system can then search the database and choose relevant items based on his or her profile (Mu 2018).

The diﬀiculty here lies in how to find user preferences based on item content. Many approaches have been developed to solve this problem in the fields of data mining or machine learning. For example, in an Article Recommender System, in order to recommend certain articles to a specific reader, the Recommender System must first obtain all the articles that the user has read before, and then the keywords can be extracted from the text using text mining methods (using TF-IDF for example). After integrating all the keywords with their respective weights, a book can be represented by a multidimensional vector. Specific clustering algorithms can then be applied to find the centers of these vectors that represent the interests of that reader. Finally, recommended articles could be obtained by computing the distance between certain candidate articles and the user's profile vector (Mu 2018).

## Collaborative Filtering-Based Recommender Systems

If our movie recommender system is implemented following the collaborative filtering approach, it means that if the user watches/likes a set of movies (say 'A', 'B', 'C', and 'D'), and there are other users watching the same movies (e.g. 'A', 'B', 'C', 'D', and 'E'). This means that the recommended list will contain movies that other users have watched and that our user has not yet watched (in our example the movie 'E').

The basic idea of collaborative filtering is that if two users rate some common items, their interests will be considered similar. If certain items exist in one user's profile but not in the other, those items can be recommended to that user. In other words, collaborative filtering is the process of recommending items using the opinions of other users. Ratings or opinions can be obtained by asking users to fill out a questionnaire, for example (Bai et al. 2019).

## Hybrid Recommender Systems

One of the different ways to build our hybrid movie recommendation system is to generate a list of candidate movies using the collaborative filtering method, and then use this list to compute the similarity between these movies and the user's profile (the movies he/she has watched before) in order to generate a sub-list containing only the movies with strong similarity.

Hybrid recommendation methods seek to achieve the best recommendation results by combining content-based recommendation methods and collaborative filtering-based recommendation methods and any other existing methods.  The combination of two or more algorithms aims to work around the limitations of individual approaches in isolation (Mu 2018).

This approach can be divided into three different types depending on the combination process (Mu 2018): 

+ **Monolithic** where the two algorithms are merged into one algorithm to be used as a single block. 
+ **Parallel**: the two algorithms run in parallel and then the two generated lists are merged using a re-ranking function. 
+ **Pipeline**: one algorithm runs first, then the second algorithm uses the elements of the generated list as candidate elements to generate the recommended list.

# Conclusion

Recommender systems are widely applied in many application areas. They are applied in: Streaming platforms to recommend videos, news platforms to recommend relevant news to users, e-commerce services to recommend products to customers, e-learning to recommend courses to students, social networks to recommend posts and advertisements to users, and job recommendations to recommend job offers to users and recommend users to companies [(Fakhfakh et al. 2017), (Kuanr et al. 2021)].

# References

+ Amine Naak (2009). “[Papyres : un système de gestion et de recommandation d’articles de recherche](https://papyrus.bib.umontreal.ca/xmlui/handle/1866/3270)”. fra.
+ Aravind, Sesagiri Raamkumar (2018). “[A TASK-BASED SCIENTIFIC PAPER RECOMMENDER SYSTEM FOR LITERATURE REVIEW AND MANUSCRIPT PREPARATION](https://www.researchgate.net/publication/323308750_A_task-based_scientific_paper_recommender_system_for_literature_review_and_manuscript_preparation)”. en. In : p. 344.
+ Goldberg, David et al. (1992). “[Using Collaborative Filtering to Weave an Information Tapestry](https://dl.acm.org/doi/10.1145/138859.138867)”. In : Communications of the ACM 35.12, p. 61-70.
+ Resnick, Paul et al. (1994). “[GroupLens : An Open Architecture for Collaborative Filtering of Netnews](https://dl.acm.org/doi/10.1145/192844.192905)”. In : Proceedings of the 1994 ACM Conference on Computer Supported Cooperative Work. CSCW ’94. New York, NY, USA : Association for Computing Machinery, p. 175-186.
+ Mu, Ruihui (2018). “[A Survey of Recommender Systems Based on Deep Learning](https://ieeexplore.ieee.org/document/8529185)”. en. In : IEEE Access 6, p. 69009-69022.
+ Kuanr, Madhusree et Puspanjali Mohapatra (2021). “[Recent Challenges in Recommender Systems : A Survey](https://www.researchgate.net/publication/346787874_Recent_Challenges_in_Recommender_Systems_A_Survey)”. en. In : Progress in Advanced Computing and Intelligent Engineering. Sous la dir. de Chhabi Rani Panigrahi et al. Advances in Intelligent Systems and Computing. Singapore : Springer, p. 353-365.
+ Bai, Xiaomei et al. (2019). “[Scientific Paper Recommendation : A Survey](https://ieeexplore.ieee.org/document/8598708)”. en. In : IEEE Access 7, p. 9324-9339.
+ Fakhfakh, Rim, Anis Ben et Chokri Ben (2017). “[Deep Learning-Based Recommendation : Current Issues and Challenges](https://www.researchgate.net/publication/322248919_Deep_Learning-Based_Recommendation_Current_Issues_and_Challenges)”. en. In : International Journal of Advanced Computer Science and Applications 8.12.