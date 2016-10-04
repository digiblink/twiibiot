# Twiibiot
Basic event based Twitter searcher/responder (eg. "twitter bot") on predefined keywords.

## INSTALLATION

* Import install/mysql_db.sql
* Copy conf/config.inc.php.sample to conf/config.inc.php
* Modify conf/config.inc.php to suit your needs (at least database information)
* Populate your database `phrases` table with prases you want to monitor
* Edit send.php and populate $responses array with your predefined responses ('response one', 'response two', ..)

## RUNNING
These scripts have to be ran from command line (do *not* host them on a public directory), ie.: 

* in screen one:
```
php -f search.php # searches for new tweets
```
* in screen two:
```
php -f send.php # replies to new tweets
```
The purpose of splitting - you can run search.php as a daemon and run send.php only when you need to (for example - based on a cronjob).

## LIMITATIONS
I'm aware that I've left try/catch statements, as Twitter API lags from time to time, and it would be nice if you could see, what exactly happened.

Also, send.php is quite buggy for now - it'll break when you try to send duplicate tweet (needs patching).

## CREDITS
Author: Kristaps Karlsons - https://github.com/skakri/twiibiot

### License
* Codebase - MPL (Mozilla Public License)
* Twitter for PHP - New BSD License
* OAuth.php - MIT
* MySQL Singleton Class - GNU GPL
