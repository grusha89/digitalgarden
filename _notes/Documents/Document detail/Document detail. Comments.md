
Comment section can be found in the left panel of document detail

When the comment section is clicked:
* comment section unfolds/folds
* comment input is auto focused

Comment input consists of:
* input itself with the placeholder "Write a comment"
* @ button to tag the user or team
* "Send" button with the tooltip "Send \[ENTER]"

Comment section icon displays the number of the comments sent as well as on the grid #comments

Actual date of the messages is displayed 
Each message displays time and the name of user who wrote the comment (user can not see own name on own comments)

#### Tagging users and teams

* users and teams can be tagged via clicking the button @ or inserting the same symbol
* when @ is inserted the list of users and teams appears:
	* users and Everyone team are displayed first, then the teams
	* full text search can be used by user/team name and the description
* when user is tagged:
	* if user who is tagged looks at the comment - button "Solve" is displayed:
		* when button "Solve" is clicked - green ticket appears with user name, date and time
	* if user who is not tagged looks at the comment he can see only "Awaiting resolution" message


### Comments limits

Limit is 500 symbols:
* when the limit is reached (more than 500 symbols) button "Send" becomes inactive and it's impossible to send the comment
* works for all kinds of the comments
	* in document detail
	* in approval process
	* on the grid

### Edit and remove comments

Each posted comment has a kebab menu that appears on hover:
* Edit - when the comment is edited it will have note "modified", clicking on "modified"
 opens a previous version of the comment
* Remove - instead of the comment "removed" note appears, clicking on "removed" reveals the comment that was deleted