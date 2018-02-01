---
layout: post
title: Incremental Learning - a continuous learning approach
comments: true
---

A few days back I read an article about how Bitcoin's price can be sufficiently explained by Metcalfe's law. As you read through the post, resist the temptation to click the links to learn more about Bitcoin, Metcalfe's law etc. (Maybe you should read about [Bitcoin][1] if you have not heard of it). I have provided all the information you need for your first read on this post.
> Bitcoin is a cryptocurrency and worldwide payment system. It is the first decentralized digital currency, as the system works without a central bank or single administrator. The network is peer-to-peer and transactions take place between users directly, without an intermediary. These transactions are verified by network nodes through the use of cryptography and recorded in a public distributed ledger called a blockchain. Bitcoin was invented by an unknown person or group of people under the name Satoshi Nakamoto and released as open-source software in 2009.

<div></div>
> Metcalfe's law states that the value of a telecommunications network is proportional to the square of the number of connected users of the system (n^2)

Following the traditional way, this is how I read the article. I start the article and partway thorough it when I come across Metcalfe's law, I read on Wikipedia about Metcalfe's law. Then while reading about Metcalfe's law, learning that there are other network laws, I start to read a bit about them. Then I come back to the article and then after reading another portion of the article, I go back to other sites to learn a bit more about Metcalfe's law. Then I diverge to another topic that says that `nlog(n)` is a better approximation for the value of a network than the `n^2` suggested by Metcalfe's law. There I learn that there are other network laws. I branch out again to learn about these laws. After spending a long time in the rabbit hole, I come back and complete the original article. This long path to completing the article makes sense if the knowledge of how to assign value to networks is going to be useful to me. Is it really worth learning about a bunch of other network laws and a replacement law for Metcalfe's law? Well, if I am having a good use for it, then a little breadth is good.  

  This leads back to the question - how do we know that this information is going to be useful in the long run? We cannot know for sure. But we can have a good heuristic to know if this information is useful. The frequency of the use of this information is a heuristic indicator of value of this information. The frequency of use is not know before hand. Only after a period of time do we know how frequently we found Metcalfe's (or the `nlog(n)`) law useful.

  If the information in the article was not something we could use, then we had spent a lot of time on it when the time could be allocated for something better.

A better approach to learn this would be like this.
1. Read the [article][3]. When you come across things you do not know about (Metcalfe's law etc), know what it is -  just sufficient to understand the article. In this case, the information in the quoted text above is enough. Finish the article. Remember at this point you do not know about the other network laws or the `nlogn(n)` unless you already knew it.
2. Later you may find no value for this information. Good that you did spend time on other things that added value to you.
3. On the flip-side, you might find use of this information. You realize that you can use that information to better estimate the value of other crypto coins, which can help you make better investment decisions. You use Metcalfe's law to determine the value of another crypto currency (say [Ethereum][6]). Now is the time to learn a bit more about [Metcalfe's law][2]. Equipped with the new information, reevaluate the value of Ethereum if you learnt anything more by exploring Metcalfe' s law. You might have learnt that it cannot be a strong [mental model][7], but a good heuristic to keep in mind.
> Ethereum is another crypto currency, which is decentralized like Bitcoin. It allows users to create smart contracts, which can be understood as building applications on top of the Ethereum blockchain.

4. You may use the law again to estimate the value of another crypto currency (say Monero). Now is the time to learn more about it. At this time you would explore the assumption in Metcalfe's law - *all users contribute equally to the network*. You try to learn if this assumption is valid in the setting of a crypto currency and based that you re-evaluate the value of Monero.
> Monero is a crypto currency like Bitcoin. It provides features for protecting the privacy of the users.

5. Beyond this point if you don't apply the knowledge anymore, then you don't learn about it. But if you find it was useful in determining the value for Ether and Monero, you apply it again (,say for Ripple). You now should spend some more time learning about this law and you would most likely end up learning about the `nlog(n)` replacement [law](4) or other [network laws](5).
6. This process goes on, with additional for every new application of the law.

Now that you got an idea of where this is headed, lets dive into the subject of this post - **Incremental Learning**.

### <u>Incremental Learning</u>
What is Incremental Learning?

It is a concept in Machine Learning which refers to training a model with additional input, to extend the learning of the model.
> In computer science, incremental learning is a method of machine learning, in which input data is continuously used to extend the existing model's knowledge i.e. to further train the model.

But in this post, **Incremental Learning** refers to a practical and effective method of continuous learning.

To begin with, lets look at how we learn something new. These are the steps we typically follow:
  1. A need to learn a new concept/technology/subject arises
  2. Collect resources (books, courses, experts) and start learning
  3. Learn till a sufficient proficiency is reached to achieve the goal in 1.

If we need to gain more expertise in the subject matter, we dig into more details when the need arises. This need-based additional learning is problematic. The problems it gives rise to are:
  1. In most cases, we need to learn a big chunk of subject matter in a short time.
  2. The new learning will produce new insights and pops out mistakes in the implementations of earlier learning. *Implementation is the application of learning. For instance, it is a programming language you are learning, your implementation is the application you build with that language. In the article mentioned earlier, the implementation is the use of the knowledge of Metcalfe's law to assign value to Ether,Monreo,Ripple etc*

When we need to learn a big chunk, it would normally be time limited. That being the case, we do not get time to digest the information we consume and hence can lead to superficial or incomplete learning. On learning a subject matter in depth, one also learns that some past implementation can be improved. This demands time and that is scarce.

To overcome these problems and get new benefits here is a better approach to learning:
Here are the step and following that I will tell why it should be done this way and the benefit it provides.
  1. Need to learn a new concept/technology/subject arises (same as before)
  2. Collect resources (books, courses, experts) and start learning (same as before)
  3. Learn till a sufficient proficiency is reached to achieve the goal in 1. (same as before)
  4. Every time the implementation is used/revisited learn one new concept in that subject matter and apply that to the current implementation

This simple approach is effective. The steps 1-3 are the same as before. We normally stop learning once we have the desired proficiency. The more we use an implementation, the need to learn more about it and improve the current implementation becomes important. But we don't realize the need till the time when our current knowledge fails us. So we need an approach to learn continuously, and also only the things that matter. We cannot tell ahead in time what matters the most in the future. A good heuristic to know the importance of subject matter is the frequency of use of its implementation. Therefore the more we use an implementation, the more important its subject matter is. The most important implementation is used more frequently than others. We have a better grasp of the subject matter that we use often. Also, we know less about the less important subject matters. By following this approach, we have spend time where it is relevant.

This approach offers some advantages over the traditional approach:
  1. In the traditional approach, as we cannot determine the exact utility of a subject matter, we cannot dedicate proper amount of time for it. Here, using a good heuristic, we can spend time on learning proportional to the use of the subject matter.
  2. The time limited requirement to learn in-depth about the subject-matter is avoided in this approach as we have already learnt what we need to. Also, here we learn small chunks in short periods of time. Hence learning is improved.
  3. We implement the new learning as we learn it and results in a better implementation than improving the old implementation at once, after a period of time. This approach does not suffer from the time crunch suffered by the traditional approach. Also, applying the new information we obtain is a better way to commit it to memory.


 Try this approach to continuous learning and voice your results in the comment box.

[1]: https://en.wikipedia.org/wiki/Bitcoin
[2]: https://en.wikipedia.org/wiki/Metcalfe%27s_law
[3]: https://www.businessinsider.com.au/bitcoin-price-movement-explained-by-one-equation-fundstrat-tom-lee-metcalf-law-network-effect-2017-10
[4]: https://spectrum.ieee.org/computing/networks/metcalfes-law-is-wrong
[5]: https://www.networkworld.com/article/2225509/cisco-subnet/understand-and-obey-the-laws-of-networking.html]
[6]: https://en.wikipedia.org/wiki/Ethereum
[7]: https://www.fs.blog/mental-models/
