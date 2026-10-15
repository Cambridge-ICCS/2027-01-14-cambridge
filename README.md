# AI Carpentry Workshop — University of Cambridge, 14–15 January 2027

This repository holds the website for the
[AI Carpentry](https://aicarpentry.org) **Learning Programming with GenAI**
workshop hosted at the University of Cambridge on 14–15 January 2027.

- **Website:** <https://cambridge-iccs.github.io/2027-01-14-cambridge/>
- **Curriculum:** [Learning Programming with GenAI](https://carpentries-incubator.github.io/coding-with-llms-novice/)
  (AI Carpentry `user-novice`)

## Maintaining the site

This repository is a fork of the
[AI Carpentry workshop template](https://github.com/aicarpentry/workshop-template)
(itself based on [The Carpentries workshop template](https://github.com/carpentries/workshop-template)).
All edits are made on the `gh-pages` branch, which GitHub Pages publishes
automatically.

The site is customised through the YAML header of [`index.md`](index.md) and
the settings in [`_config.yml`](_config.yml) — see the
[Carpentries customisation instructions](https://carpentries.github.io/workshop-template/customization/index.html)
for full details. Before pushing changes, run `make workshop-check` to
validate the page.

To pick up future improvements to the template, pull from the `upstream`
remote (`aicarpentry/workshop-template`) and merge into `gh-pages`.
