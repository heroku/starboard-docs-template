# Starboard documentation template

This repository is a small example of the format used by [starboard][1]

Clone this repository and add your own onboarding/offboarding/crossboarding guides.

## What is the Documentation Repo format?

It needs first a `data.json` file. This file is the core of the parser. It gives the documents needed per team and a few other metadata information.

```
{
  "teams": {
    "id": "Heroku",
    "slug": "heroku-teams",
    "additional_paths": ["", "/extra"],
    "children": [
        {
            "id": "Engineers",
            "slug": "engineers",
            "children": []
        },
        {
            "id": "Marketing",
            "slug": "marketing"
        }
    ]
  },
  "lists_order": ["Pre-Hire", "First Day", "First Week", "First Month"]
}
```
- `Teams` is a tree representing the teams in your company.
  - `id` is actually the name of the team.
  - `slug` the slug name low caps no spaces. This is used to find the markdown file with the lists.
  - `additional_paths` is an array of other places where markdown file for this team are located.
  - `children` an array of sub-teams.
- `lists_order` is the order of the different lists the board will contain.

## What is the files hierarchy?

Onboarding files for a team will be all the files per team up to the root.
So if you are in the team `engineers` you will have the onboarding files of engineers and heroku-teams. Also the different `additional_paths` of these two.

For the team engineers, we expect to have `heroku-teams/engineers/onboarding.markdown`, `heroku-teams/onboarding.markdown`, `onboarding.markdown` and `extra/onboarding.markdown`.
These files will be located in the root of the repo.
If a file is missing, starboard will just skip it.

## File format

See the root onboarding.markdown for an example.

[1]: http://github.com/heroku/starboard