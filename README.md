# gsd-submissions (private)

Inbox for outside submissions to Global Sociology Digest. Issues here are opened automatically by the
submission forms on the Journal Guide Site (`components/journal-guide/site/src/submissions` and
`public/submit` in `neowangzc/gsd-academic-services`). Keep this repository private:
comments hold submitters' contact details.

## What arrives

| Labels | From | Body |
|---|---|---|
| `site:opportunities`, `type:job` | Post a job | `## ` sections, then a `## Data` JSON block (`gsd-job-submission/v1`) |
| `site:conferences`, `type:conference` | Submit a conference | an optional "Conference details" block, then the board's `## ` sections (`gsd-submission/v1`) |
| `site:conferences`, `type:correction` | Report an error on the board | the board's sections |

Every new issue also has `status:triage`, and a first comment with the submitter's email, name and affiliation.

## Reviewing

1. Check the details against the official posting or conference page.
2. Label the issue `approved`, `needs-info` (email the submitter) or `declined`, and leave a short reason.
3. Approved items go through the normal data pipelines and their checks; they are not published from here.
   Conferences: `node cli.mjs inbox pull --github --repo neowangzc/gsd-submissions` in
   `components/conferences/socsci-pipeline`.
4. Once an item is live, label it `published` and close the issue.

Never copy contact details into data, commits or other repositories.
