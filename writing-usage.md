
# Writing Usage

* story dir
  * story-cli list
  * optional: story-cli new <story>
  * story-cli clone <story>
  * cd ~/stories/checkouts/<story>
    * or: story-cli cd <story-fragment>
  * make
  * make view
* setting up the environment
  * all in the story directory
  * tty 0: emacs
  * tty 1: build / sc-im
  * tty 2: "w3m duckduckgo.com"  "w3m wikipedia.com" searching
* tagging
  * Reach some milestone
  * commit all changes
  * git tag -a draft-1 -m "first draft"
  * git tag
  * git push origin draft-1
* emacs (general)
  * M-c capitalize the following word
    * the point must be at the beginning of the word or on the space
      before the word. Use prev and next word to align.
  * M-l convert the following word to lower case
  * C-x 2 split window horizontally
    * C-x 0 back to one window
* emacs jinx
  * M-x jinx-correct-all
  * M-$ triggers correction for the word under point (jinx-correct)
    * "?" to bring up the window showing corrections and shortcuts
    * One or two digits selects an existing dictionary correcting option
    * @ adds to global, personal dictionary
      * Add very few words here. Things like my last name.
    * / adds it to the directory
      * most corrections go here
    * '*' adds it to the current file (in a comment at the end of the doc)
      * few corrections go here
    * '+' adds it to the session
      * I'm not even sure what this is
    * M-n M-p next and previous misspelled word
* markdown
  * '#' for chapter's
  * three hyphens for section breaks
  * use the html entity &emdash; to display an em dash
* w3m
  * B back up to previous page
  * s popup buffer selection
* sm-im
  * the packaged version doesn't work; you need to compile from the
    latest github source
  * ":q" to quit
  * ":h" help
  * arrows to move around
  * "=" "e" insert/edit a numeric value
    * editing is crazy; better to delete with x and re-enter
    * can replace a single char with r
  * "\" "E" insert/edit a text value
  * "x" delete a cell value
    * also deletes formatting
  * ":w filename.sc" save in sc format
    * ":w" to write from then on
  * "v" select a range
  * "a a" widen column to largest value
  * "fl" and "fh" to widen and shorten
  * ":set autowrap" to have text go multiple lines
  * "fr" freeze row "ur" unfreeze row "fc" freeze column "uc" unfreeze column
  * "yy" copy (yank) cell; "p" paste cell; "Pc" paste relative cell reference; "Pf" paste formatting
  * ':format "format string"'
    * e.g. :format "00%"
    * integer with commas: ""
    * currency: 
    * percent: 
* tig
  * pacman -S tig
  * tig
  * tig --word-diff
  * tig --word-diff story.md
  * h for help
  * major views
    * m main
    * s status
    * l log
    * r refs
    * b blame
  * enter on commit hash
  * tab moves between windows
    * this doesn't seem to do what I think it does
  * "l" maximizes the log view
  * "q" backs out of menus and eventually quits

# Debian / Chromebook

* list, add, and remove, wifi networks with nmcli
  * nmcli con show
  * shows all network configurations
  * nmcli wifi list
  * show all available wifi networks
  * nmcli dev wifi connect SSID password PASSWORD
  * nmcli con down CONFIGURATION
  * nmcli con up CONFIGURATION
