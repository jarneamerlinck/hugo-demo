+++
draft = false
date = 2024-05-12T23:04:14+02:00
title = "Setup Hugo for a personal website"
description = "Creating a personal website with Hugo and cloudflare pages"
slug = ""
authors = ["jarneamerlinck"]
tags = []
categories = []
externalLink = ""
series = []
+++
# Setup Hugo for a personal website
This is a quick guide on how to create a personal blog with [hugo](https://gohugo.io), [github](https://github.com) and [cloudflare pages](https://pages.cloudflare.com/).

Steps:

1. [Create a new hugo project](#create-a-new-hugo-project)
2. [Github repository](#github-repository)
3. [Activate cloudflare pages](#activate-cloudflare-pages)

> P.S.
>
> If you have questions or need help just send a message.


## Create a new hugo project

First you need to install hugo. See the official [page](https://gohugo.io/installation/windows/#package-managers) on how to do it.
you'll also need git.

When you have it installed you can create a new hugo project.

There are 2 ways to do this

- Create a new Hugo project
- Fork this [example repo](https://github.com/jarneamerlinck/hugo-demo)


Make sure you can push to a repo that is public on github (or gitlab) as this is needed for cloudflare pages.


## Github repository

For the github repository the requirements are simple:
It needs to be public.




## Activate cloudflare pages

For this step you'll need a cloudflare account.

visit [dash.cloudflare.com](https://dash.cloudflare.com/login) and create the account.


Then you need to go to the ´workers-and-pages´. If you can't find it you can add ´workers-and-pages/create/pages´ to the end of the url.

Next is the following steps:

1. Connect to git.
2. Select your repository
3. Set the following options
    a. select the branch that is used to deploy ´main´ or ´master´
    b. ´Framework preset´ to ´hugo´
4. Save and deploy


Then go to deployment.

On this page you can find the public URL to visit your site. Mine ends with ´pages.dev´




## Making a fist page

in the root of the repo run
```bash
hugo new post/name_of_file.md
```

This will create a new markdown file with the default template.

Now you can edit that markdown file with any editor you want. Save and push to git or deploy localy to test out with

```bash
hugo server -D
```

the ´-D´ at the end is needed to view pages that are still in draft form.

These will not be public.

If you want to change a page from draft to publish you can do that in the frontmatter (the first few lines) of the markdown file

```markdown

+++
draft = false
date = 2024-05-12T23:04:14+02:00
```

change `draft = true` to `draft = false`

Then just commit and push and it will be public.
