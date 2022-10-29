# Idea: Software Notifier service
 
Use case: I need a way of keeping track of software releases that is package, 
format or distribution agnostic. It would have some sort of notification system
such as through Slack, Discord, SMS, etc. 

I struggle to keep on top of all the versions of CLI tools, dependencies and 
other critical components required to do my job as a cloud engineer and 
developer. It seems like tools or services exist for particular tool chains
such as for security vulnerabilities of OSS. I have no intention of rewriting
something that a security vendor provides as a full-blown product.

Maybe this is just nagware that seems convenient to me because I can't stay
organized.

A/C:
- Provide a list of open source projects or application dependencies to keep 
  track of. Needs to conform to Semver and be inspectable (Maven coordinates,
  npm package, GitHub project releases, etc).
- Select either real-time updates (tell me as soon as a new release lands),
  or some type of cron-like interval (daily/weekly/month/quarterly).
- Provide webhook/callback URL to POST notifications via JSON to integrate
  with CI/CD.
- Slack bot/app (send to workspace & channel)
- Discord bot (send to server & channel)
- SMS (stretch, maybe too intrusive)

## Prior Art
- Email (lol), mailing lists. I find these hard to keep track of and I would
  prefer something that is more programmatic such as an API with webhooks or
  callbacks. I want a real-time message (like email) or some sort of daily
  communication that rolls up important (but not crtical/security related)
  updates.
- [Novu](https://docs.novu.co/overview/introduction/). It's possible I could
  write something on top of Novu to handle the actual communication or 
  notification channels. 
- [release-notes.com](https://release-notes.com/). This looks to be almost
  exactly what I'm thinking of. Unfortunately, this looks to have been 
  abandoned since [2018](https://github.com/release-notes/release-notes-hub/commits/master). Possible starting point.
- [PagerDuty](https://www.pagerduty.com/). This is more for incidents but
  still worth noting here. If I was just writing this for $enterprise, this
  would make the most sense to target their APIs.

