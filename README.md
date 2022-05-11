# Amazon_NLP_SSBooks


Opinion Mining and Sentiment Analysis on Consumer Reviews of Social Science Books
Problem Statement
The tremendous expansion of e-commerce websites and companies (Amazon, E-bay, etc.)  around the globe enabled people to buy various products ranging from technological ones to books and express their feelings and opinions about them. The common practice among these merchants is to allow their customers to write reviews about the products alongside rating them numerically. However, the massive number of textual reviews written every hour in companies like Amazon complicate keeping track of their customers' thinking about their products. Conventionally, some domain experts of customer satisfaction both in academia and industry focus on mining and sentiment analysis of these user-generated reviews (Hu and Liu; Dave, Lawrence, and Pennock 2003; Hu and Liu). Influential names of this literature such as Steve Lawrence, David M. Pennock, Minqing Hu and Bing Liu broadly aim to mine the features of the product on which the customers have expressed their opinions (Feature-based Opinion Summary)(Kang and Zhou, n.d.). There are also some domain research (Liu, Hu, and Cheng 2005) in which experts tried to create topic sentiment mixture model(Liu, Hu, and Cheng 2005; Mei, Shen, and Zhai 2007; Zhang and Lim, n.d.; Rana, Cheah, and Letchmunan 2016; Mei et al. 2007; Korfiatis et al. 2019; Reisenbichler and Reutterer 2019) by integrating the two method. Besides, some common techniques used in this domain are including but not limited to FBS (Feature-Based Summarization), using opinion words in extracting product features (Calheiros, Moro, and Rita 2017), Double Propagation method and LDA (Hu, 2005). However, despite some advances, the problem of constituting feature-based summaries of customer reviews and answering the questions of which features of products that consumers expressed their opinions and perceptions persist. Even though domain experts from industry and academia endeavor to make meaningful information extraction from their customers via several methods, this task needs to be developed further by integrating NLP's cornerstone methods of topic modeling and sentiment analysis. 
Research Question
In this respect, my research question pertains to understanding and extracting the opinions and sentiments of consumers who bought books about the core disciplines of social sciences (Economics, Anthropology, Sociology, Political Science, and Psychology) via Amazon and wrote reviews at a specific time period. Mainly, I wonder how we can develop an efficient model capable of clustering and identifying the reviews written about these sold social science books? To what extent are there substantial sentimental differences and subject-based/thematic variation across reviews written for these disciplines? Also, is there a hidden pattern about topics that (author, content, publisher, etc.) are more prominent in the customer reviews of these books? Therefore, by utilizing NLP and integrating several methods, I hope to develop a model with a high degree of precision and obtain various insights regarding these questions.
Data
Amazon publicly provides a rich source of information and collection of reviews written in the amazon.com (USA) marketplace and associated metadata for academic researchers in the fields of Natural Language Processing (NLP), Information Retrieval (IR), and Machine Learning (ML). Among this open source datasets provided by Amazon, I will focus on the book dataset harboring more than three million unique reviews written by consumers on the books they bought between 1995 until 2015. In addition to book titles and individual reviews, I also will utilize some useful features like star rating (five Likert scale) to assess the precision of my sentiment analysis. Besides, my intention is not to extract, label, and or classify all the social sciences books in the dataset. Instead, I will try to take a sample of social sciences books in data through designating the particular discipline of a book by whether its title contains name of any social science discipline such as politics and psychology.
Methodology
The central aim of this study is to take a sample from consumer reviews written for social sciences books and answer the question that to what extent there is a significant sentimental differences and subject-based variation across these reviews in various disciplines of social sciences such as psychology, politics and sociology. The very first task for the purpose of this study is to conduct a sentiment analysis identifying the polarity of a given text. There are different implementations and techniques of sentiment analysis such as labeling the data into positive, negative and neutral or labeling with more sophisticated and specific emotion types such as anger, joy, sadness and so forth. In this study, I will use a pre-trained sentiment analysis model available on huggingface library: Bert-base-multilingual-uncased-sentiment (https://huggingface.co/nlptown/bert-base-multilingual-uncased-sentiment). This bert base model is particularly fine-tuned for sentiment analysis on product reviews in six languages, the largest of which is English. This pretrained model has been proven to be highly accurate on 5,000 held-out product reviews. After fitting the model to Amazon dataset, I will calculate the accuracy and F score (which are popular and widely used as evaluation metrics for sentiment analysis) in addition to random manual check to see how well the model is doing.
Another part of this study is to inspect and uncover latent themes and topics as to understand what consumers are talking about the book they bought as and whether there is a variation or differences in reviews written for different disciplines of social science books. For the purpose of this task, I will be implementing topic modeling technique through specific method of ‘‘Latent Dirichlet Allocation’’ (LDA) which I decided to do so by following the comprehensive and useful decision tree for topic modeling (Vayansky and Kumar 2020). Basically, LDA structures the data in three level of word, topic and document and trats documents as built on randomized mixture of hidden topics. After fitting LDA to model and getting distinct themes from it, topic model evaluation will help to reflect on whether identified topics are coherent and understandable or interpretable by humans. One conventional metric to be used in this study to evaluate the topic model will be ‘held out log-likelihood’ (i.e. perplexity). However, because of the limitations of this metric (Wallach et al. 2009), I will also focus on Topic Coherence Measures as an evaluation methodology which uses conditional likelihood of the co-occurrence of words in a topic through calculating the degree of semantic similarity between high score words in a specific topic (Röder, Both, and Hinneburg 2015). This coherence pipeline will enable to distinguish between topics that are semantically different and interpretable by humans. Lastly, to delve more into the human interpretability of the topic model and control for spurious words or topics, I will evaluate topics by considering word or topic intrusion techniques (Lau, Newman, and Baldwin 2014).
Finally, another aim of this study is to integrate topic modeling and sentiment analysis as to see sentiment levels for each topic. Hence, after fitting the model and evaluating its performance, I will pursue a manual road to integrate the two models. First, I will sort out and debug the topic model after obtaining sentiments of my documents through Bert-base-multilingual-uncased-sentiment. Later on, I will aggregate which particular topics correspond to particular sentiment, thereby reaching to the information about the sentiments of every distinct topic derived from consumer reviews of a sample of social science books sold in Amazon.

Literature Research
1.	Calheiros, Ana Catarina, Sérgio Moro, and Paulo Rita. 2017. “Sentiment Classification of Consumer-Generated Online Reviews Using Topic Modeling.” Journal of Hospitality Marketing & Management 26 (7): 675–93. https://doi.org/10.1080/19368623.2017.1310075.
2.	Dave, Kushal, Steve Lawrence, and David M. Pennock. 2003. “Mining the Peanut Gallery: Opinion Extraction and Semantic Classification of Product Reviews.” In Proceedings of the Twelfth International Conference on World Wide Web  - WWW ’03, 519. Budapest, Hungary: ACM Press. https://doi.org/10.1145/775152.775226.
3.	Hu, Minqing. n.d. “Opinion Feature Extraction Using Class Sequential Rules,” 6.
4.	Hu, Minqing, and Bing Liu. n.d. “Mining Opinion Features in Customer Reviews,” 6.
5.	Kang, Yin, and Lina Zhou. n.d. “Extracting Product Features from Online Consumer Reviews,” 8.
6.	Korfiatis, Nikolaos, Panagiotis Stamolampros, Panos Kourouthanassis, and Vasileios Sagiadinos. 2019. “Measuring Service Quality from Unstructured Data: A Topic Modeling Application on Airline Passengers’ Online Reviews.” Expert Systems with Applications 116 (February): 472–86. https://doi.org/10.1016/j.eswa.2018.09.037.
7.	Lau, Jey Han, David Newman, and Timothy Baldwin. 2014. “Machine Reading Tea Leaves: Automatically Evaluating Topic Coherence and Topic Model Quality.” In Proceedings of the 14th Conference of the European Chapter of the Association for Computational Linguistics, 530–39. Gothenburg, Sweden: Association for Computational Linguistics. https://doi.org/10.3115/v1/E14-1056.
8.	Liu, Bing, Minqing Hu, and Junsheng Cheng. 2005. “Opinion Observer: Analyzing and Comparing Opinions on the Web.” In Proceedings of the 14th International Conference on World Wide Web  - WWW ’05, 342. Chiba, Japan: ACM Press. https://doi.org/10.1145/1060745.1060797.
9.	Mei, Qiaozhu, Xu Ling, Matthew Wondra, Hang Su, and ChengXiang Zhai. 2007. “Topic Sentiment Mixture: Modeling Facets and Opinions in Weblogs.” In Proceedings of the 16th International Conference on World Wide Web  - WWW ’07, 171. Banff, Alberta, Canada: ACM Press. https://doi.org/10.1145/1242572.1242596.
10.	Mei, Qiaozhu, Xuehua Shen, and ChengXiang Zhai. 2007. “Automatic Labeling of Multinomial Topic Models.” In Proceedings of the 13th ACM SIGKDD International Conference on Knowledge Discovery and Data Mining  - KDD ’07, 490. San Jose, California, USA: ACM Press. https://doi.org/10.1145/1281192.1281246.
11.	Rana, Toqir, Yu-N Cheah, and Sukumar Letchmunan. 2016. “Topic Modeling in Sentiment Analysis: A Systematic Review.” Journal of ICT Research and Applications 10 (June): 76–93. https://doi.org/10.5614/itbj.ict.res.appl.2016.10.1.6.
12.	Reisenbichler, Martin, and Thomas Reutterer. 2019. “Topic Modeling in Marketing: Recent Advances and Research Opportunities.” Journal of Business Economics 89 (3): 327–56. https://doi.org/10.1007/s11573-018-0915-7.
13.	Röder, Michael, Andreas Both, and Alexander Hinneburg. 2015. “Exploring the Space of Topic Coherence Measures.” In Proceedings of the Eighth ACM International Conference on Web Search and Data Mining, 399–408. Shanghai China: ACM. https://doi.org/10.1145/2684822.2685324.
14.	Vayansky, Ike, and Sathish A.P. Kumar. 2020. “A Review of Topic Modeling Methods.” Information Systems 94 (December): 101582. https://doi.org/10.1016/j.is.2020.101582.
15.	Wallach, Hanna M., Iain Murray, Ruslan Salakhutdinov, and David Mimno. 2009. “Evaluation Methods for Topic Models.” In Proceedings of the 26th Annual International Conference on Machine Learning - ICML ’09, 1–8. Montreal, Quebec, Canada: ACM Press. https://doi.org/10.1145/1553374.1553515.
16.	Zhang, Lei, and Suk Hwan Lim. n.d. “Extracting and Ranking Product Features in Opinion Documents,” 9.


