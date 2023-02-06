# nixpkgs-watcher

notifications for my favorite apps

generate more user-involvement in nixpkgs issues and PRs

## watch repo

github has the "watch repo" feature, where i can select "all activity". if i do this for nixpkgs, this will flood my inbox with 100s of mails every day

i want something similar, but i want notifications \*only\* for my favorite apps. for example, i use the kde plasma desktop, so i want notifications for issues and PRs dealing with this app

## meta.maintainers

existing solution: somepackage.meta.maintainers. but i dont want to be a "maintainer", i just want to "watch" my favorite apps

## challenges

### fetching

get a feed of nixpkgs notifications, but not to my email inbox. maybe matrix chat protocol? the whole feed should be sent to my machine, so i can do the filtering offline

### filtering

maintain a list of my favorite apps. installed apps, github stars (useful for packages that are not-yet in nixpkgs), ... this is used to filter the feed from nixpkgs

### labeling

map issues to packages. maybe: parse package from issue title. maybe: have a bot to auto-generate labels like `pkgs.plasma-desktop` (if the auto-generated label is wrong, aka false positive, it can be manually fixed by "someone")

### too much

too many notifications. then let me "filter by random", similar to chatroulette ... nixpkgs-roulette?

## implementation

something browser-based, because github is in the browser

or a fork of the github-desktop client?

## similar problems

### collaborative editing

collaborative editing of github PRs. github's PR interface makes this hard, but making patches to PRs should be simple and fun

## see also

### watch git commits

different than [How to 'Watch' only a directory in a GitHub repository?](https://stackoverflow.com/questions/9732779/how-to-watch-only-a-directory-in-a-github-repository) because they watch commits, but not issues or PRs

### stats and trends on github issues and PRs

https://discourse.nixos.org/t/stats-trends-on-github-issues-prs/7936

<blockquote>

raboof:

we recently hit 4000 open nixpkgs issues, which made me curious about the trends in those numbers. I wrote a [quick script ](https://github.com/raboof/github-open-issues-per-month) to get them from the API and break them down per month

</blockquote>

<blockquote>

jonringer:

Ultimately, we just need more people reviewing PRs (not necessarily committers, but it can be frustrating to have a PR polished and no committer to push the button). But the work is largely unrewarding (unless it affects you), and can be very time-intensive.

</blockquote>

<blockquote>

zimbatm:

It would be great if it was possible to “subscribe” to a package more dynamically. Interest doesn’t map 1:1 with the git history. Sometimes I package a thing because I want to go in a direction, then loose interest.

</blockquote>

<blockquote>

Ekleog:

feed per package so that people would be able to subscribe to the ones of interest to them

</blockquote>

<blockquote>

renatoGarcia:

if i had sooner received some message or read in someplace that my reviews would be useful even i being a newcomer, i would had started to post reviews to my packages earlier.

</blockquote>

<blockquote>

musicmatze:

github does not scale for nixpkgs

</blockquote>

<blockquote>

Thra11:

we need better tools to match issues and PRs to interested parties in a more dynamic / *casual* manner.

Sometimes, I have some spare time, so I think, “maybe I’ll take a look at some nixpkgs issues/PRs”. I sit down, open up the nixpkgs issues or PRs page on github, and start reading the titles. There are over 4000 open issues / 2000 open PRs, so I know there are plenty that I can contribute to in there somewhere. However, after scanning the first 10 or so pages, I’ve seen a lot of things I am not interested in or know nothing about

[...]

After a few pages of items which aren’t interesting to me, I usually give up. As a result, my main way of finding issues and PRs at the moment is to wait until I have a problem or want something packaged, then check if there are any related issues or PRs. An then once the issue is fixed, I forget about it, whereas I’d often be happy to look at similar issues in the future.

</blockquote>

### triage-stale-issues-and-prs-automatically

https://discourse.nixos.org/t/triage-stale-issues-and-prs-automatically/1809

<blockquote>

arianvp:

Currently nixpkgs has thousands of stale issues and PRs

</blockquote>

### suggestion-to-help-maintainers-with-nixpkgs-prs-bloat

https://discourse.nixos.org/t/suggestion-to-help-maintainers-with-nixpkgs-prs-bloat/4794

[quote="doronbehar, post:5, topic:4794, full:true"]
I’m not implying that not enough PRs are merged. I’m implying that there are too many and it makes it unfeasable to distinguish between those worth attention and those not.

</blockquote>

<blockquote>

doronbehar:

I don’t see why should we implement this our selves from scratch within ofborg (https://github.com/NixOS/ofborg/pull/216). From a Google search and a GitHub’s Marketplace search, I’ve found these alternatives which might interest us:

* https://github.com/facelessuser/label-bot - not a one click install GitHub App, but I think you’ll like [this feature](https://github.com/facelessuser/label-bot#lgtm).
* https://github.com/marketplace/trafico-pull-request-labeler - Seems to implement most of what we want automatically, besides letting non committers change labels with comments as in [facelessuser/label-bot#lgtm](https://github.com/facelessuser/label-bot#lgtm).
* https://github.com/marketplace/actions/label-approved-pull-requests - Implements only a subset of the features we’d like to have but still worth mentioning in this list.
* https://github.com/marketplace/devbots-needs-review - Again, implements only a subset of the features we’d like to have but still worth mentioning as it may be coupled with other bots / actions for completeness.

Also for issues, there are some interesting apps:

* https://github.com/marketplace/issue-label-bot - The most interesting one in this list IMO.
* [https://mlbot.net/ ](https://mlbot.net/)
* [https://github.com/apps/responder ](https://github.com/apps/responder)

</blockquote>

### RFC 30

https://github.com/NixOS/rfcs/pull/30

### issue 41793

https://github.com/NixOS/nixpkgs/issues/41793

> [RFC51](https://github.com/NixOS/rfcs/blob/master/rfcs/0051-mark-stale-issues.md) added a stale bot, which I think addresses the main actionable issue in the original post

### is-git-github-the-appropriate-tool-for-us

https://discourse.nixos.org/t/is-git-github-the-appropriate-tool-for-us/12474

<blockquote>

jonringer:

Nix doesn’t really have a technology issue, it has a people issue. There’s just too few trusted people in this purely volunteer organization to handle the overhead of issues and PRs.

</blockquote>

### queues-lets-make-something-a-tad-better-than-prs-already-reviewed-prs

https://discourse.nixos.org/t/queues-lets-make-something-a-tad-better-than-prs-already-reviewed/17541

### the-best-way-to-attract-attention-to-issues-and-pull-requests

https://discourse.nixos.org/t/the-best-way-to-attract-attention-to-issues-and-pull-requests/1130

### nixpkgss-current-development-workflow-is-not-sustainable

https://discourse.nixos.org/t/nixpkgss-current-development-workflow-is-not-sustainable/18741

<blockquote>

samuela:

In Nixpkgs, anyone at any time can break any of your packages. Recently, the latest `staging` , `staging-next` , and `python-updates` branches were merged into `master` resulting in thousands of new commits breaking about half of all packages that I require in my day-to-day job.
[...]
These changes are made without any substantive form of CI (nixpkgs-review, etc) and oftentimes without even a peer-reviewed PR.
[...]
How is a package maintainer expected to know when someone else breaks their build?
[...]
The current system is simply not sustainable for downstream package maintainers, especially considering that these breaking changes come with no prior notice, no migration plan, and no alerting of failures.

</blockquote>

