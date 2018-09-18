# Text Processing and Sentiment Analysis of Twitter Data

## A complete guide to text processing using Twitter data and R.

![](https://cdn-images-1.medium.com/max/2000/1*IorOGvtVhDcaReiPXpmDgA.jpeg)

Shameless plugin: We are a data annotation platform to make it super easy for
you to build ML datasets. Just upload data, invite your team and build datasets
super quick. [Check us out.](https://dataturks.com/index.php?s=blg)

*****

### Why Text Processing using R?

With the increasing importance of computational text analysis in research , many
researchers face the challenge of learning how to use advanced software that
enables this text analysis. Currently, one of the most popular environments for
computational methods and the emerging field of “data science” is the R
statistical software. However, for researchers that are not well-versed in
programming, learning how to use R can be a challenge, and performing text
analysis in particular can seem daunting. In this step by step guide one can
learn that performing text analysis in R is not as hard as some might fear. This
is an introduction into the use of common techniques, with the aim of helping
researchers get acquainted with computational text analysis in general, as well
as getting a start at performing advanced text analysis studies in R.

### **Why R?**

R was specifically designed for statistical analysis, which makes it highly
suitable for data science applications. Although the learning curve for
programming with R can be steep, especially for people without prior programming
experience, the tools now available for carrying out text analysis in R make it
easy to perform powerful, cutting-edge text analytics using only a few simple
commands. One of the keys to R’s explosive growth has been its densely populated
collection of extension software libraries, known in R terminology as packages,
supplied and maintained by R’s extensive user community. Each package extends
the functionality of the base R language and core packages, and in addition to
functions and data must include documentation and examples, often in the form of
vignettes demonstrating the use of the package. The best-known package
repository, the Comprehensive R Archive Network (CRAN), currently has over
10,000 packages that are published.

Text analysis in particular has become well established in R. There is a vast
collection of dedicated text processing and text analysis packages, from
low-level string operations to advanced text modeling techniques such as fitting
Latent Dirichlet Allocation models, R provides it all. One of the main
advantages of performing text analysis in R is that it is often possible, and
relatively easy, to switch between different packages or to combine them. Recent
efforts among the R text analysis developers’ community are designed to promote
this interoperability to maximize flexibility and choice among users.4 As a
result, learning the basics for text analysis in R provides access to a wide
range of advanced text analysis features.

### **Why Twitter Data?**

Twitter is an online microblogging tool that disseminates more than 400 million
messages per day, including vast amounts of information about almost all
industries from entertainment to sports, health to business etc. One of the best
things about Twitter — indeed, perhaps its greatest appeal — is in its
accessibility. It’s easy to use both for sharing information and for collecting
it. Twitter provides unprecedented access to our lawmakers and to our
celebrities, as well as to news as it’s happening. Twitter represents an
important data source for the business models of huge companies as well.

All the above characteristics make twitter a best place to collect real time and
latest data to analyse and do any sought of research for real life situations.

If you need other datasets, you can download pre-exiting datasets of various use
cases like cancer detection to Q&A dataset to sports comments to chatbots. Here
is various [text classification
datasets.](https://dataturks.com/projects/Trending?type=TEXT_CLASSIFICATION)

Or if you have your unique use case, you can create your very own dataset for
it. You can download images from the web and to make a big dataset in no time,
use an annotation tool like [Dataturks](https://dataturks.com/), where you
upload the raw data and tag manually in a ziffy.

![](https://cdn-images-1.medium.com/max/1600/1*TP3yMw05n_uGPkhoAclo-Q.png)

### **Dataset:**

In order to extract data of Twitter we need to create a Twitter Application.

**STEPS TO CREATE A TWITTER APPLICATION**

1.Navigate to My Applications. ([Link](https://apps.twitter.com/))

![](https://cdn-images-1.medium.com/max/1600/1*kOkCkQsas21DXzmwxYmvJw.png)

2. Since I already have this app created, it appears on my page. Click on
“create New App”.

![](https://cdn-images-1.medium.com/max/1600/1*pUi69BAo52q_EPVYfmF7JQ.png)

Fill in all the details of the application.

3. Once all the details are filled in and verified you will be granted the
customer and access keys.

![](https://cdn-images-1.medium.com/max/1600/1*hEJCkSCXDVyUQx6Rl7V8xA.png)

![](https://cdn-images-1.medium.com/max/1600/1*tsh5JxYz2HFrnxKZQGDWsQ.png)

**INSTALL AND LOAD R PACKAGES:**

R comes with a standard set of packages. A number of other packages are
[available for download](http://cran.us.r-project.org/) and installation. For
the purpose of this post, we will need the following packages:

– ROAuth: *Provides an interface to the OAuth 1.0 specification, allowing users
to authenticate via OAuth to the server of their choice.*

– Twitter: *Provides an interface to the Twitter web API.*

Let’s start by installing and loading all the required packages.

Connect your twitter account to R, in order to extract the required tweets.

### **Extracting tweets using a particular hashtag:**

Convert this extracted data to a dataframe which makes it more readable and
easier to work with.

Here is how the data would look like:

![](https://cdn-images-1.medium.com/max/1600/1*HTOjT30Tw4BxLiiR24UCNw.png)

It is very clear that in the text section of the data, which is what we need to
process there are a lot of special characters and unnecessary data which we
would not require. Hence it becomes extremely important to pre-process this data
and then we can continue with out analysis.

Below is a code to pre-process the data and remove tabs, blank spaces, links
etc. This section can be modified according to one’s requirements.

### **A little more pre-processing — Removal of stop words!**

### What are Stop Words?

When working with text mining applications, we often hear of the term “stop
words” or “stop word list” or even “stop list”. Stop words are basically a set
of commonly used words in any language, not just English. The reason why stop
words are critical to many applications is that, if we remove the words that are
very commonly used in a given language, we can focus on the important words
instead.

Stop words are generally thought to be a **“single set of words”**. It really
can mean different things to different applications. For example, in some
applications removing all stop words right from determiners (e.g. the, a, an) to
prepositions (e.g. above, across, before) to some adjectives (e.g. good, nice)
can be an appropriate stop word list. To some applications however, this can be
detrimental. For instance, in sentiment analysis removing adjective terms such
as ‘good’ and ‘nice’ as well as negations such as ‘not’ can throw algorithms off
their tracks. In such cases, one can choose to use a minimal stop list
consisting of just determiners or determiners with prepositions or just
coordinating conjunctions depending on the needs of the application.

We are done pre-processing our data, and are ready to do some analysis.

Data visualizations (like charts, graphs, infographics, and more) give analysts
a valuable way to communicate important information at a glance. If you want a
stunning visualization format to highlight important textual data points, using
a word cloud can make dull data sizzle and immediately convey crucial
information.

### **What are Word Clouds?**

Word clouds (also known as text clouds or tag clouds) work in a simple way: the
more a specific word appears in a source of textual data (such as a speech, blog
post, or database), the bigger and bolder it appears in the word cloud.

So let’s generate some word clouds and find out some of the frequent and
important terms being used in the tweets we have extracted.

Below are the word clouds for the data I have:

![](https://cdn-images-1.medium.com/max/1200/1*t9fUJEbQqMHF7cuomVmjRg.png)

![](https://cdn-images-1.medium.com/max/1200/1*RHlnUEb61lCd3Be8I9i8Og.png)

![](https://cdn-images-1.medium.com/max/1200/1*kUrnBU3mX562_QxSka7mow.png)

![](https://cdn-images-1.medium.com/max/1200/1*D4UByym-wenTIwt67QSePg.png)

Next I will be doing sentiment analysis on the tweets.

### **Introduction to Sentiment Analysis:**

### What is Sentiment Analysis?

Sentiment essentially relates to feelings; attitudes, emotions and opinions.
Sentiment Analysis refers to the practice of applying Natural Language
Processing and Text Analysis techniques to identify and extract subjective
information from a piece of text. A person’s opinion or feelings are for the
most part subjective and not facts. Which means to accurately analyze an
individual’s opinion or mood from a piece of text can be extremely difficult.
With Sentiment Analysis from a text analytics point of view, we are essentially
looking to get an understanding of the attitude of a writer with respect to a
topic in a piece of text and its polarity; whether it’s positive, negative or
neutral.

In recent years there has been a steady increase in interest from brands,
companies and researchers in Sentiment Analysis and its application to business
analytics. The business world today, as is the case in many data analytics
streams, are looking for “business insight.”

In relation to sentiment analysis, I am talking about insights into consumer
behavior, what customers want, what are customers like and dislike about the
products, what their buying signals are, what their decision process looks like
etc because in the end of the its the customers for whose satisfaction these
businesses work for.

I have used the inbuilt sentiment analyzer in R, which uses the NRC sentiment
dictionary to calculate the presence of eight different emotions and their
corresponding valence in a text.

From the following plot of sentiment analysis on tweets with #Google, its
observable that Google has a positive impact on the consumers and is extremely
trusted by them. There have lately been quite a good number of anticipations
maybe on their products or the company employee’s or any other possibility.

![](https://cdn-images-1.medium.com/max/1600/1*pY55rC6UeujBSGeK8hIidw.png)

From the following plot of sentiment analysis on tweets with #Amazon, its
observable that the E-Commerce giant, has maximum tweets being positive and
similar to google has won the trust of consumers. Apart from these there is a
notable amount of joy among their customers.

![](https://cdn-images-1.medium.com/max/1600/1*oz5NhvYqLeOEYKx5CF5neA.png)

The tweets with #Facebook show a little different trend. Lately, there seems to
be a lot of negative sentiment associated with the tweets on facebook. But along
with that there is also a trust which the company has maintained.

![](https://cdn-images-1.medium.com/max/1600/1*GIHrpZOxo0NfRKmJq1NfTw.png)

In general, the tweets on technology have a lot of positivity and trust among
the people, across the globe.

![](https://cdn-images-1.medium.com/max/1600/1*rPZPhNnVqqd9slPHOvTAlA.png)

These are only a few very obvious sentiments which I have described. You can
always look at the visualizations and draw multiple conclusions about the data.

### **Conclusion:**

Text Processing and Sentiment analysis emerges as a challenging field with lots
of obstacles as it involves natural language processing. It has a wide variety
of applications that could benefit from its results, such as news analytics,
marketing, question answering, readers do. Getting important insights from
opinions expressed on the internet especially from social media blogs is vital
for many companies and institutions, whether it is in terms of product feedback,
public mood, or investors opinions.

Sentiment analysis is a difficult technology to get right. However, when you do,
the benefits are great.

Look for a tool that has uses Natural Language Processing technology and ideally
with machine learning capabilities. Look for a vendor that treats sentiment
analysis seriously and shows advancements and updates in their sentiment
analysis technology.

### [DataTurks: Data Annotations Made Super Easy](https://hackernoon.com/@dataturks)

Data Annotation Platform. Image Bounding, Document Annotation, NLP and Text
Annotations. #HumanInTheLoop #AI, #TrainingData for #MachineLearning.
