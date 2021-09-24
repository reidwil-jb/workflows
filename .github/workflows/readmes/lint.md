## Lint

The lint.yaml workflow is built for analytics teams who have github repositories for their SQL code ([dbt](https://www.getdbt.com/), [snowchanger](https://github.com/phdata/snowchange/blob/master/snowchange.py)). 
It is smart enough to find only new files from the pull request relative to the default branch on the repository (main, master, development). It will lint those files and return a tidy comment on the pull request.

It currently is dependent on:

  💠 action/checkout@v2
  
  💠 [SQLfluff](https://github.com/sqlfluff/sqlfluff) for linting
  
  💠 [Khan's pull request trigger](https://github.com/Khan/pull-request-comment-trigger)
  
  💠 [octions's post comments](https://github.com/maxkomarychev/octions#read-input-from-file)
  
## How To:

To trigger this action you must type `/lint` on a pull request comment. If you want to change the trigger, adjust [here](https://github.com/reidwil-jb/workflows/blob/main/.github/workflows/lint.yml#L21)

You should see a rocket 🚀 emote on your comment and subsequently message like:
````
-------------
Diff Quality
Quality Report: sqlfluff
Diff: remotes/origin/develop...HEAD, staged and unstaged changes
-------------
models/star/bookings_rt/views/vw_pnr.sql (100%)
-------------
Total:   49 lines
Violations: 0 lines
% Quality: 100%
-------------
