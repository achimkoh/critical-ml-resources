--
title: Black Box
permalink: /blackbox
--

# Black box

Machine learning algorithms are becoming increasingly important elements of the computational processes operating in the contemporary society, in fields such as finance, journalism, advertising, medicine, education, translation, robotics, and much more. Along with the prospect of efficiency through automation and new possibilities in the field of artificial intelligence, this technological change also raises concerns about the sociopolitical aspects of the change. If machine learning-related technology is increasingly being used in ways that affect people's lives—for example to make decisions on whether someone should be eligible for a loan, be granted a bail, or be diagnosed of a certain disease—the social implementations will benefit from a transparent knowledge of the technology. Fittingly, a recurring concern in the critical discourse around machine learning points to its opacity, its being a 'black box': you feed some data to the machine, it outputs some result, but we don't really know what happens inside.

The black box metaphor can mean different things, which in turn may require different ways of thinking about them. For example, most governmental administrative procedures that I have to deal with certainly feel like black boxes. Electronic gadgets that are almost impossible to open up are also in a sense black boxes. In both cases, the metaphor works because I don't have access to the inside workings of the system, and even if I had, I wouldn't have enough knowledge to understand what is going on. But are these all of the obstacles? In other words, can the problem of opacity be countered by having access and expert knowledge?

In the case of machine learning, there exists another layer of opacity which adds complexity to our current concern. To set up a perspective, here I will borrow from Jenna Burrell's article that provides a useful framework to articulate what opacity is. Burrell distinguishes three forms of opacity with regards to algorithms in general, and especially machine learning algorithms:

- intentional concealment by (mostly) companies and governments
- technical illiteracy
- complexity of machine learning models themselves, in addition to that of data and code

### Opacity as secrecy

One reason that algorithms can be opaque is because their owners, often corporations, are willingly keeping it a secret against adversaries. Such a strategy could serve to protect intellectual properties, evidently, but also to maintain a certain level of product quality. For example, search engines deliberately do not reveal their exact ranking mechanisms for search results; otherwise it would be too easy for the adversary (in this case, a content provider) to 'game' the system to draw more attention to their web page. Nobody wants a search engine which returns a flood of spam. 

Such a secrecy could also be a means of concealing illegal or frowned-upon activities. For example, a company might write in their code some tricks to manipulate consumers and unjustifiably discriminate them, and have such activities undiscovered under the protection of intellectual property laws.

### Opacity as illiteracy

Coding and designing algorithms is a specialized skill. Open-sourced code can still be very hard to understand, especially to a non-programmer. Somewhat like how a legal document full of legal jargon would be impenetrable by non-experts, the difficulty of understanding the computer science adds another layer of opacity.

### Opacity caused by the scale and complexity that we use algorithms

Some algorithms are hard to understand, even when we have access and the expertise. Look at Google search's page source and you will be dazzled by the amount of code that runs the seemingly simple white page with not much else than a logo and a search box. And this is only the front end; one can imagine that the code running on Google's servers, that actually does the information retrieval, is much lengthier. It is also not a single program but a combination of multiple components, too, which would make understanding the code even harder.

But wait, there's more. If such complexity can be achieved through traditional, explicit rule-based programming, the statistical approaches of machine learning models take the problem a few steps further. Machine learning algorithms learn on training data and in the process tweak their internal logic. This process can be automated and run in a large scale very quickly, which makes machine learning algorithms very effective in tasks like classification. 

(E.g. Let's say we have a million examples each of which we know the values of several thousand different variables, and which one of two categories each example falls into. Given a new example and the values of its several hundred variable, but with its category unknown, can we mathematically decide which category this new example is most likely to belong to? This would be very tedious, or near impossible to do by hand, but machine learning algorithms can deal with such a problem quite well)

The process of a machine learning algorithm making its decision based on some data, is perhaps not too difficult to understand as a whole. But its internal specifics, such as how a certain variable (also referred to as feature or dimension, disregarding the technical differences for now) influences the result, is not necessarily friendly to human comprehension. Human explanation tends to rely on semantics; we assign meanings to why and how some things happen. But the mathematics of optimization that underlie machine learning does not really care for meanings—what it wants is to get to the right result. The neural network that recognizes dog faces does not look for their eyes.

The problem of dimensionality (i.e. there are so many variables that a machine learning algorithm has consider, that it is (a) inefficient to calculate and (b) hard to understand what's going on) adds to the problem. Also, the relation between a variable and the decision made might not be linear. Some variables may seem to have no influence when looked at separately, but in fact have an influence in a combined manner. When we train machine learning algorithms, data points (e.g. emails) are represented using a number of variables (e.g. words in the email dataset). We can also calculate what variables have the biggest influence on the decision (e.g. is this email spam or not?). But looking at the top 10 most influential words*, for example, may not tell you much (or could even be misleading) in terms of understanding what the algorithm is doing with its thousands of features as an aggregate.

\* *This is not to say that looking at the most influential features is pointless. Some algorithmic auditing methods rely on it, such as the FairML toolbox mentioned below. But the example provided in FairML uses 11 features, while text-related applications can rely on many thousands of features! What Burrell's example shows is that what can seem intuitively like a good approach might not be of much help depending on the data and model we are looking at.*

[//]: # (Machine learning is like external hunch. Based on one's experience and instinct, one develops an intuitive sense of what comes towards them, even if they haven't seen anything like it before. But it can be really hard to explain why a specific thing led to a certain intuitive decision. That's the realm of psychoanalysis, and if you are like me, reflecting on what exactly is happening in one's mind is difficult! )

[//]: # (Perhaps intuition relies to the body as much as it does to the mind. Maybe it is one of the reasons why we can't relate that much to or even recognize what artificial neural networks 'see.')

[//]: # (I know anthromorphism is warned against, but I find it interesting to compare machine learning / AI to the workings of my mind because it gives me an opportunity to reflect on how I think. For example, dimensional reduction and 환유, where a small thing stands for a much bigger set of things)

### Strategies of engagement

The different types of opacity call for different, or mixed modes of engagement. Ways to deal with abusive intentional secrecy may include auditing the source code, possibly via regulations; auditors independent from conflicts of interests could provide a way protect intellectual properties in spite of the audit. Sandvig et al. also lay down audit designs that wouldn't require access to the code, for example by scraping the platform, employing dummy user accounts or hiring some users to participate in the research. Such efforts should be concurrent with an education for computational literacy, and efforts from the field to write 'good' and legible code. 

Machine learning also has a sort of "fundamental opacity," that cannot be easily overcome by just having access to source data and code. Burrell notes some approaches that the designers of the machine learning models could take: not using machine learning in specific domains is actually one of them, as well as techniques to simplify the models such as feature reduction. In addition to these approaches that aim at making it easier to understand why the model is doing certain things, she also notes other approaches that focus more on evaluating what the model does from an outside point of view. To look at whether a classifier has discriminatory effects, one could feed a wide range of different data and see how it performs, without having to explicitly interpret the inner logics in a human-comprehensible way. Different methods of algorithmic auditing are being researched, and some of them are also becoming more accessible such as the [FairML](https://github.com/adebayoj/fairml) toolbox by Julius Adebayo.

### Implications

EU's General Data Protection Regulation, effective 2018, is known for its implementation of the "right to be forgotten." Another thing it does is regulating the use of "automated individual decision-making, including profiling," by which EU highlights the citizen's right towards an explanation regarding algorithmic decisions. We can expect lots of discussions and political power plays in the legal, technological, economic and many more fields around machine learning. While such strong measures are not being taken in the US to my knowledge, calls for interdisciplinary discussion and participation in policymaking are being made here as well. As machine learning technology is increasingly widely applied, the ability of the society to wield it for the collective good becomes ever more important. Articulating why opacity can be problematic, educating researchers and practitioners as well as the greater public about its implication, and engaging in measures to mitigate the problems will require the collective effort of people from diverse fields.

## References and further readings

- Burrell, Jenna. "How the machine ‘thinks’: Understanding opacity in machine learning algorithms." Big Data & Society 3, no. 1 (2016): 2053951715622512.  
- Sandvig, Christian, Kevin Hamilton, Karrie Karahalios, and Cedric Langbort. "Auditing algorithms: Research methods for detecting discrimination on internet platforms." Data and discrimination: converting critical concerns into productive inquiry (2014).  
- http://www.fatml.org/resources  
- https://www.are.na/critical-machine-learning/black-boxes
