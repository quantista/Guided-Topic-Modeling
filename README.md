# Guided-Topic-Modeling
Guided Topic Modeling (GTM) enables the generation of comprehensive topic clusters (i.e. topic dictionaries) for a broad range of topics.

**Requirements:**  
* Python 3.11.4
* Conda
* Packages in requirements.yaml

**Installation**  
*Create a new virtual environment: conda 

The command-line interface is as follows:


**Further notes**
*All words in the vocabulary are lowercase


## Documentation

### Topic Generation

To generate your own topic you have to define two (positive) seed words that are indicative for a certain topic. For example, if you want to generate the topic "family" you could define the seed words "mother" and "father". Alternatively using "family" and "parents" or something similar would also be possible. Thus, you define two words that are both related to the desired topic.

### Parameters

The GTM algorithm is designed to give the user control over the topic characteristics by specifying the parameters: seed word weights, negative seed words and the gravity parameter.

**Weights**
Each seed word is associated with a weight parameter, which is initially set to 1.0. By increasing the weight of one seed word over the other, the generated topic will be more closely centered around the word with the higher weight. If we for example define the seed words "iphone" with a weight of 2.0 and "steve_jobs" with a weight of 1.0 the topic will be centered around the concepts smartphone/iphone/electronic devices. Try it out to get a feeling. Usually, weights above 2 are not necessary.

**Negative Seed Words**
Sometimes unwanted words appear in a topic. One solution for that would be the manual deletion of undesired words from the topic. Another option is to define negative seed words, i.e, words that should not be included in a topic. These negative seed words are associated with negative weights. Sensible values range from -0.1 to -0.5. For example if you try to generate the topic "recession" by defining the seed words "recession" and "crash" (cluster size = 100, gravity=0.15) you will notice the word "deadly_crash" appearing in the topic. This is because the word crash has multiple meanings, financial crash or car crash for example. We can avoid words unrelated to financial crashes by defining the negative seed word "deadly_crash" (e.g. weight = -0.3). With that, the topic is fully centered around the concept of a financial crash. An alternative solution would be to think about other, less ambiguous seed words.

**Gravity**
Gravity allows to control how easily the topic is allowed to drift away from the initial seed words. If gravity is chosen to be very high (> 0.5) the topic will very likely stay centered around the initial seed words. If gravity is very low (e.g. 0) the topic will find a new center that is less determined by the seed words. Sensible values for gravity are in the range 0.05 to 0.2.

**Topic Size**
Topic size is pretty much self-explaining, it defines the number of words collected for a specific topic.


