## Commands for basic read and write text files
- touch notes.txt: makes notes.txt file 
- echo "Line 1" > notes.txt: "Line 1" redirects to notes.txt
- echo "Line 2" >> notes.txt: "Line 2" redirects to notes.txt
- echo "Line 3" >> notes.txt: "Line 3" redirects to notes.txt
- echo "Line 4" | tee -a: displays "Line 4" on terminal and appends "Line 4" to notes.txt
- echo "Line 5" | tee -a: displays "Line 5" on terminal and appends "Line 5" to notes.txt
- head -n 2 notes.txt: gives top 2 lines of notes.txt
- tail -n 2 notes.txt: gives bottom 2 lines of notes.txt
