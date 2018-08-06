---
layout: post
title: Scripting the Day Away
date: 2018-08-06 07:00:00
categories: scripts python
---

**If you have to do it more than once, script it!**

Not only does automating your mundane daily tasks allow for more time to focus on the fun stuff, it also reduces the possibility for errors.

You may be asking, how can I possibly script all of my daily tasks?

The answer is APIs!

## Using APIs:

Scripting the mundane is faster and easier with the data we can get from APIs.

Here are some example APIs I interacted with to get my Pull Request links and added them to my User Stories.

#### GitHub's API:

First, I can get all open Pull Requests using [GitHub's API](https://developer.github.com/v3/) into a JSON format:
```python
import requests
import json

result = requests.get('https://api.github.com/repos/Organization/Repository/pulls?state=open', auth=(username, password))
pullRequests = result.json()

```

#### VersionOne's API:

Now that I have my Pull Request, I can add the link to a User Story using the [VersionOne.SDK.Python](https://github.com/versionone/VersionOne.SDK.Python):
```python
from v1pysdk import V1Meta

userStory = v1Meta.Story.where(Number=self.V1ID).first()
userStory.ResolutionDetails = '<p><a href="' + link + '">' + link + '</p>'
v1Meta.commit()
```

Using the GitHub API along with the VersionOne API, I can take the mundane task of linking my Pull Requests to User Stories and make it automated with a script.

But now, I'm sure you are thinking, does that just mean I have to run a script every day now?

Not true! With Window's Task Scheduler, I can make my script run as often and frequent as I want.

## Setting up a Task in Window's Task Scheduler:

1. Open Task Scheduler
1. In the Actions panel, select `Create Task...`
1. In the Actions tab, select `New...`
1. From here you can add your script to run:
![Actions Tab]({{ site.baseurl }}/assets/2018-08-06/ActionsTab.JPG)  
**FYI: `.pyw` extension allows you to run your python script silently**
1. In the Triggers tab, you select when it will run and how often:
![Triggers Tab]({{ site.baseurl }}/assets/2018-08-06/TriggersTab.JPG)  
This is where you have the freedom to customize when your script will run.  
You can even run it every time you log into your computer.

After this, I no longer have to even think about the mundane process of linking my Pull Requests to my User Stories.

Now, if only I could write a script for my mundane tasks in real life. #MowinTheLawnInTexas