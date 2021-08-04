# Obsidian to Anki Python Script 
A python script that converts markdown files to Anki note/flash cards.
deck_name: java

## Road map
### Short term
- vocabulary words to Anki
- adding images to Anki cards
	- if its a basic reverse card note, add the image on both front and back card
- normal hierarchical notes to Anki
- code highlighting to Anki
	- might need to fork Anki code highlighting add-on and integrate it with Anki Connect add-on
	- https://pygments.org/docs/quickstart/
- Color code answers as green and questions as bold the front and back of flash card
	- Color code flash cards using HTML tags 

### Long term
- Updates from Anki sync with Markdown file via the update method, by checking if the markdown parsed note is equal to the anki note.
	- In other words, two way sync
- add a Extra field to note cards for hierarchical notes
	- maybe have "Extra" notes in Obsidian not have '-' at the beginning of the note, to denote that it is not part of the hierarchical notes (child or parent)

## Notes
delete note

: <!!---ids:234234---!!>
asdfupdate note
C :: D <!!--id:234234--!!>
create new note
C :: D

## Notes
In Anki, use Anki tag, `Obsidian`, when searching for note cards that have been added via `Obsidian to Anki` python script.

Motivation:
- Convert hierarchical structured Obsidian MarkDown notes into Anki note cards for easy recall.
