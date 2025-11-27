![](image/Title.png)

## Table of contents
[1. Introduction](#introduction)<br>
[2. Word clouds](#four-lenses-of-climate-discourse)<br>
[3. Sentiment Prediction](#can-we-predict-climate-sentiment-from-text)<br>
[4. Discussions](#what-all-this-says-about-public-climate-discourse)<br>
[5. Conclusion](#why-is-this-matter)<br>

## Introduction
Forget think pieces that hand-wave about climate change. <br>
What happens when you actually read tens of thousands of real conversations about it?

That’s what this project set out to explore: nearly 44,000 climate-related tweets (2015–2018), pre-labelled with sentiment, analysed with R to understand how people talk about climate change, who they blame or trust, and how hopeful or hopeless they sound.

<img src="image/image22.jpg">

__What people talk about when they talk about climate change__

At the core of the dataset is a now-familiar story: most people accept that climate change is real, human-driven, and dangerous. But what’s interesting isn’t just whether they believe in it—it’s how they frame it, and who they see as responsible.

#

Scanning the tweets, several big themes stand out:

__- Everyday causes and global consequences__ <br>
  People connect climate change to cars, fuel, deforestation, and industry—but also to floods, extreme weather, sea level rise, and ecosystem collapse. Climate change is framed less as a distant scientific problem and more as an ongoing global crisis touching health, livelihoods, tourism, and food systems.

__- Human-made crisis, human-made responsibility__ <br>
Tweets consistently point the finger at overdevelopment, resource extraction, and weak or absent policy. The villains aren’t abstract “emissions” but governments, corporations, and political leaders who refuse to act.

## Four lenses of climate discourse

Using word clouds across the dataset, you start to see four overlapping “worlds” of conversation:

![](image/data3.png)

![](image/data4.png)

__- Media & celebrity climate discourse__ <br>
Words like “film,” “documentary,” “leonardo,” “dicaprio” show just how strongly documentaries and celebrity advocates shape attention. Climate change here is seen through storytelling: big, emotional narratives, films, and viral clips driving awareness and urgency.

__- Non-media, everyday debate__ <br>
In more general conversations, terms like “trump,” “government,” “science” pop out. People talk about climate change by talking about leadership, facts, and public policy. It’s less “is climate change real?” and more “why is our government ignoring the science?”

__- Science as anchor__ <br>
Words such as “scientists,” “study,” “data” reveal an expectation that climate claims should be backed by evidence. People cite research, reports, and expert consensus. Science becomes a status marker: if you have “data” and “study” on your side, you’re seen as credible.

__- Politics as battleground__ <br>
The political word cloud is predictable but intense: “trump,” “president,” “republican”. Climate change is deeply politicised, entangled with party identity and presidential rhetoric. Many conversations are less about CO₂ and more about what political allegiance says about your stance on reality itself.

#

__Between hope and doom__

One of the most intriguing contrasts in the data is emotional tone:

![](image/data5.png)

__On the hopeful side (Positive + Solutions):__ <br>
Words like “policy,” “solution,” “regulation” signal that many people still believe in institutional fixes. There’s faith that strong policies, international agreements, and state action can shift the trajectory.

__On the doom side (Negative + Problems):__ <br>
Words including “flood,” “crisis,” “extinction” indicate deep anxiety and a sense of looming catastrophe. Climate change isn’t a “future risk” in these tweets; it’s an unfolding emergency and an existential threat.

Public opinion lives in the tension between these two: hope that something can be done, and fear that we are already too late.

## Can we predict climate sentiment from text?

The project also tries something bolder: building a model to automatically predict how people feel about climate change based on their tweets.

Using a labelled dataset of __43,943 tweets__ with __sentiment scores (-1, 0, 1, 2)__, the team:

- Built a __Document-Term Matrix (DTM)__
- Trained a Naive Bayes classifier in R (with packages like __caret, e1071, ggplot2, tidyverse__)
- Evaluated how well the model could guess tweet sentiment

![](image/data6.png)

The hard truth: the model isn’t great. <br>

The results are refreshingly honest:

- Overall accuracy: about __0.385__
- No-information rate (just predicting the majority class): __0.523__

→ Meaning: a dumb baseline that always guesses the most common sentiment does better than the trained model.

- Kappa: __0.183__, suggesting limited real agreement beyond chance.

![](image/data10.png)

The model does best on the __more positive class (sentiment = 1 and 2)__, and much worse on neutral or negative tweets. <br>
It tends to misclassify subtle differences—like mixing up “mildly supportive” with “very supportive.”

![](image/data8.png)

Even individual words behave in unexpected ways. For example, __“global”__ skews negative in the model, likely because it frequently appears in anxious phrases like “global crisis” or “global catastrophe,” not in neutral global references.

![](image/data7.png)

## What all this says about public climate discourse

Stepping back from the numbers and word clouds, a few big patterns emerge:

__Belief is not the main battle anymore__ <br>
Most people in this dataset aren’t arguing whether climate change is real. They’re arguing about responsibility, urgency, and what to do—and often, who is lying or failing.

__Narratives beat raw data—but data still matters__ <br>
Films, celebrities, and vivid imagery capture attention. At the same time, “study,” “data,” and “scientists” are powerful anchors in arguments. Culture pulls people in; evidence helps keep them there.

__Politics shapes how we talk about the planet__ <br>
Climate conversations are inseparable from politics. Who you trust, what media you watch, and which leaders you follow deeply colours your climate narrative.

__Emotion isn’t easily reduced to labels__ <br>
This dataset’s sentiment labels (-1, 0, 1, 2) and a simple model are not enough to fully capture how people feel about climate change. Fear, anger, moral outrage, cautious optimism—these don’t fit neatly into four bins.

## Why is this matter?

Social media is messy, biased, and absolutely not a perfect proxy for “public opinion.” But it does act as a real-time, global focus group: a place where fears, hopes, and myths about climate change surface publicly.

Our project shows:

__- There is widespread recognition of climate change as a human-made crisis.__ <br>
__- People place huge weight on institutions—governments, leaders, scientists, media outlets—to interpret and act on climate risk.__ <br>
__- Simple sentiment prediction models, on their own, are not enough to forecast how public attitudes will evolve.__ <br>

If we want to understand and shift public opinion on climate, we need richer methods and better data: cross-platform comparisons, geographic and temporal context, and more sophisticated models that can handle nuance and politicisation.

Until then, climate discourse on social media will remain what it already is: a chaotic but revealing mirror of a world that knows it’s in trouble—and can’t yet agree on how to get out.

