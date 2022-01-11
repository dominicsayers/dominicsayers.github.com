---
layout: post
title: Choosing an open source component
date: 2021-01-11 08:00:00 +0000
image: dependency_title_inverted.png
thumbnail: dependency_component.png
tags:
  - featured
---
Before I approve the use of an open source component in one of my projects, there are some simple checks I ask the team to do before we use it. These are the checks we do - you may have others, in which case I'd love to hear about them. Hit me up in the comments or on social media.

## License

Open source licensing is often straightforward but can occasionally get a bit complicated and you need to assure yourself that the license under which the component is published is compatible with how you intend to use it.

If you're making some commercial software and incorporating open source components in it then this should be part of your due diligence before you sell your software or a service based on it.

*Most* open source software is compatible with a commercial project although you may have to credit the authors and make a copyright declaration in your code and in your app. I won't discuss individual licenses here and any further details are beyond the scope of this piece.

## Security

Any manifest security issues are a red flag - you should not use a component if it has security issues.

- **Unresolved vulnerabilities**: check for [outstanding CVE records](https://cve.mitre.org/cgi-bin/cvekey.cgi?keyword=nokogiri). It's OK for a component to have had vulnerabilities in previous versions but not in the current version, especially if the vulnerability has been known about for a long time.

## Project health

Open source software is safe and secure so long as there are many eyes reviewing the code and a body of contributors who actively address issues. This can be assessed by reviewing the project's source code home page, often on GitHub or GitLab.

- **Unmerged PRs**: lots of unmerged changes submitted by potential contributors is a sign that the project is not really active from the maintainer's point of view
- **Open issues**: lots of unanswered questions and issues is a sign that the maintainers are not giving the project as much attention as it needs
- **Recent commits**: a lack of recent commits may mean the project is end-of-life.
- **Number of contributors**: a one-person project has two problems, a lack of eyes on the code to spot vulnerabilities and a single point of failure for the project's lifecycle. If the central person abandons the project it dies.

## Contributor background

- **Basic profiling**: More of a feeling than a rule, but for instance a sudden influx of contributors from one country may be a sign of inappropriate activity. On the other hand it might just reflect a new trend in that country's engineering community. But beware.

## Project gatekeepers

- **Recent change of maintainer**: there have been examples of respectable projects turning into malware when a maintainer hands over the reins to somebody else. Something to check.

## Users

- **Public sector users**: if this open source project is used by public sector bodies they may have done some due diligence of their own. On the other hand they may not.
- **Major corporate users**: it's dangerous to assume that major corporates would always do due diligence before using an open source component, but it's reassuring nonetheless to see a component in widespread corporate use.
- **Domicile of significant users**: if a piece of open source software is used exclusively or for the most part by people or organizations from a country where you would not wish to do business, that may be a warning sign.
