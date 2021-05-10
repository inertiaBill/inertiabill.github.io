## Requirements

I was looking for a website where I could document my projects.
I was hoping to make this public to make access simple for me.
If others could benefit from this information, that would be
a bonus.

### Blog support

My initial use case was to sharing information using a
blog format.

### Markup language

Markdown is how I write. I didn't want to spend any time on
any other markup language.

### Hosting

There are many cost effective hosting solutions these days such
as,

- [Host a Static Site using Linode Object Storage](https://www.linode.com/docs/guides/host-static-site-object-storage/).
- [How To Deploy a Static Website to the Cloud with DigitalOcean App Platform](https://www.digitalocean.com/community/tutorials/how-to-deploy-a-static-website-to-the-cloud-with-digitalocean-app-platform).

As interesting as self-hosting is to me, I wasn't looking for any
administrative work at this time.

### Workflow

The workflow needed to be easy and with minimal overhead.
Since my code is already in GitHub, it seemed like 
[GitHub pages](https://docs.github.com/en/pages/getting-started-with-github-pages/about-github-pages)
with Jekyll was a good experiment.

## Creating site.

### Create the repository

Create a repo. I was looking for user site. This is done by naming
the repository (repo) USERNAME.github.io.

`git clone https://github.com/inertiaBill/inertiabill.github.io.git`

Since I was building a user site, the root of the Jekyll setup can
be the root of the repo. If the site was added to an existing
repo, then the Jekyll files would normally be rooted in /docs folder
instead.

### Enable GitHub pages

Enable GitHub pages in the setting for the repo.

### Apply a theme

Without a theme, GitHub pages will convert Markdown pages to
web pages. However, all the navigation would need to be setup
manually. Since I was looking for basic blog features like
grouping by date, tag, and with support for previous/next,
a theme was required.

There are lots of themes to choose from on
[Jekyll themes website](https://jekyllthemes.io/jekyll-blog-themes). 
At this time I was looking for I was looking primarily
for a [blog theme](https://jekyllthemes.io/jekyll-blog-themes)

I have seen two ways to setup themes. One is using the themes
gem. The benefit of this is it is easier to track changes to theme.
The other is to copy the files into the site repo. You could do
this by forking, downloading, and cloning. Check theme documentation
and license of options.

I decided to use the Minimal Mistakes theme. Since it includes a
bunch of extra sample files that I didn't want, I cloned it.

`git clone https://github.com/mmistakes/minimal-mistakes.git`

I switched to the root of the inertiabill.github.io repo and
copied just the theme files of interest.

```
cp -r ../../minimal-mistakes/_data/ .
cp -r ../../minimal-mistakes/_includes/ .
cp -r ../../minimal-mistakes/_layouts/ .
cp -r ../../minimal-mistakes/_sass/ .
cp -r ../../minimal-mistakes/assets/ .
cp -r ../../minimal-mistakes/_config.yml .
cp -r ../../minimal-mistakes/Gemfile .
cp -r ../../minimal-mistakes/index.html .
cp -r ../../minimal-mistakes/package.json .
```

## Customize website

Some basic website configuration is needed.

_config.yml : Site wide settings. Review them. Don't forget to update the author.


_data/navigation.yml : Contains navigation elements. Main is for the navigation along the top. You can enable a single level sidebar on the left with some extra front-matter

```YAML
sidebar: 
  title: "Test sidebar nav"
  nav: my-nav
```
