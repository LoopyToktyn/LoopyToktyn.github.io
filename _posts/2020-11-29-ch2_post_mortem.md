# I built a thing

## Summary
Through significantly greater tribulation than I anticipated, I've completed (as much as I intend of) the project! 
The grand result is a non-exported model that can tell you with ~85% accuracy whether it's looking at an Octane,
Mantis, Artemis, Scarab, or Dominus. The model has particular troubles correctly predicting the Mantis and is
occasionally too eager to predict something as an Octane. 

## Hurdles
There were a number of additional hurdles I faced! 
- The fastbook/fastai libraries are out of date with some very recent Bing service migrations.
- Couldn't get Gradient notebooks to pull in terminal-entered ENV variables
- Bad data + Cleaner tool efficiency
- Local setup!

#### Bing
I was eventually able to resolve this using Bing's sample Python code for interacting with their API using the Python
'request' library.

#### Gradient
I gave up. I didn't want my API Key in my notebook at all, but whatever. I've just removed it after the fact.

#### Cleaner --> Local Setup
After training my first model, having a 40%+ error rate, and then running it through the cleaner, I learned two things:
I have a lot of bad data, and this cleaner is not a good tool for quickly cleaning up hundreds of pictures. So I
considered, what could I do to make this less painful? I sure wish I could just use a Windows folder browser or something
to just easily look at, quickly click on, and mass-delete these things...

So that's what I decided to do, leading us into the local setup! At first I wanted to try to download straight from
here to my local machine, but apparently mass-download isn't an option. But I've got Python, right? Let's boot up VS Code, copy over
the few cells from the Notebook that do the image downloading, and experience success! 

Also not quite as simple. My code uses the fastai Path structure, and I didn't feel like writing my own file management
stuff, so..."Path not a defined Object" or something. We better install fastai...oop, we need torch...oop, we need fastbook...
oop, we should be using Conda...oop, we should be using a Conda environment, not base Conda...oop, VS Code not using correct
interpreter...hmm, what is CUDA?...oop, `download_images` has issues on my Windows when n_processors > 1...

At the end of the day, I now have a Jupyter environment and the fastbook/fastai libraries successfully running on my
machine within VS Code! It's a good day.

## The Model
As mentioned in the Cleaner section, the initial model was plagued with bad data, and I wasn't satisfied with my results. After cleaning
the data and running it again, we got the 85% mentioned in the summary. This isn't as good as I would have liked, but I'm satisfied
with the improvement after the work I put in.

Top losses showed some significant confusion between Artemis and Mantis. My guess would be the similar front windshields. There were
also a lot of eager guesses for the Octane -- My intuition suggests a connection between toppers and the Octane's spoiler.

I've decided not to follow through with building and deploying an iPython widget GUI app for this. At least not yet. I'm
a web dev at the moment with enough experience in deploying and styling apps. I'll likely build something nice when I feel
I have something nice I want to show off. 

## How do you feel?
Yo, I'm ready for CH3. Let's go.
