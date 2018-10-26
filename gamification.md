# Programming Gamification

## Daily Rewards

How to design a daily rewards algorithm?

With one table, three columns:
- update the `last_reward_login_date` (or just `last_login`)
- calculate the difference - if it's within a day, increment the `days_in_a_row`, else set it to 0
- if the `days_in_a_row` > `longest_consecutive_login`, update the `longest_consecutive_login`

With one database:
- every new login will create a new row. This enables one to calculate consecutive logins

If we fix the rewards (say, user can only get 30 rewards for the month), we can design the system in such a way that the system encourages total login times and not consecutive login times, so a player will not revert to day 1 if they miss a day.

## Points, badges, leaderboards (PBLs)

## References

- https://yukaichou.com/marketing-gamification/six-context-types-rewards-gamification/
- http://www.gamasutra.com/blogs/WilliamGrosso/20160613/274759/The_Science__Craft_of_Designing_Daily_Rewards__and_Why_FTP_Games_Need_Them.php
- https://www.sitepoint.com/building-engaging-web-apps-game-mechanics/
- https://designmodo.com/gamification-examples/
