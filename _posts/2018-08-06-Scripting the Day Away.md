---
layout: post
title: Scripting the Day Away
date: 2018-08-06 07:00:00
categories: scripts python
---

If you have to do it more than once, script it!  

Not only does automating your mundane daily tasks allow for more time doing the fun stuff, it also reduces the possibility for errors.

With APIs and strong community support we can getting data we need to make scripting the mundane faster and easier.

## Using APIs:

#### GitHub's API:

Here is an example getting all open Pull Requests using [GitHub's API](https://developer.github.com/v3/) into a JSON format:
```python
import requests
import json

result = requests.get('https://api.github.com/repos/Organization/Repository/pulls?state=open', auth=(username, password))
pullRequests = result.json()

```
Now that I have all my Pull Requests, I can automatically add them to my User Stories with another API.

#### VersionOne's API:

Here is an example of adding a link to a User Story using the [VersionOne.SDK.Python](https://github.com/versionone/VersionOne.SDK.Python):
```python
from v1pysdk import V1Meta

userStory = v1Meta.Story.where(Number=self.V1ID).first()
userStory.ResolutionDetails = '<p><a href="' + link + '">' + link + '</p>'
v1Meta.commit()
```

Using the GitHub API along with the VersionOne API, I can take the mundane DevOps process of linking my Pull Requests to User Stories and make it automated with a script.

Then I can add my script to Window's Task Scheduler and never have to worry about that mundane task again.

## Set up Task in Task Scheduler:

1. Open Task Scheduler
1. In the Actions panel, select `Create Task...`
1. In the Actions tab, select `New...`
1. From here you can add your script to run:
![Actions Tab]({{ site.baseurl }}/assets/2018-08-06/ActionsTab.JPG)  
**FYI: `.pyw` extension will run your python script silently**
1. In the Triggers tab, you select when it will run and how often:
![Triggers Tab]({{ site.baseurl }}/assets/2018-08-06/TriggersTab.JPG)  
This is where you have the freedom to customize when your script will run.
YOu can even run it every time you log into your computer.

After this, my script to link my pull requests to my user stories is completely automated and I no longer have to worry about that mundane process.

Now, if only I could write a script for my mundane tasks in real life.