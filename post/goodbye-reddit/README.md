# pds-backup-viewer

This is a Web-based viewer for content exported by [my fork of Power Delete Suite](https://github.com/aarmea/PowerDeleteSuite).

## Usage

It expects the following URL parameters:

* `user`: The Reddit user that the backup was generated for. The script will look for a file named `reddit_backup_{user}.csv` that the content will be loaded from.
* `permalink`: The [URI-encoded](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/encodeURIComponent) link to the content, as provided by Power Delete Suite. The script expects the exact link as it was exported using the `%encoded_permalink%` parameter -- it does not attempt to parse it at all.

A valid URL could look something like this:

<https://aarmea.github.io/pds-backup-viewer/reddit_backup.html?user=iamthatis&permalink=https%3A%2F%2Fold.reddit.com%2Fr%2Fapolloapp%2Fcomments%2F14dkqrw%2Fi_want_to_debunk_reddits_claims_and_talk_about%2F>

Provided these parameters, it will load and render the content:

TODO: Screenshot

## Known issues

* It requires Javascript. This is *by design*: I usually dislike when pages require Javascript just to load text, but in this case I do not want the content to be easily scraped.
* It loads the *entire* CSV file to display one piece of content. My Reddit backup is only 300 Kb, and it wasn't worth writing another script to split this up. There is already sharding based on the `user` -- I wouldn't mind a pull request to shard based on the `permalink` as well.
* It looks bad. You can read it, right?
