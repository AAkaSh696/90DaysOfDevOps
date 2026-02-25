## Day-10 Challenge

## Files Created
- devops.txt
- notes.txt
- script.sh
- project (directory)

## Permission Change 
- devops.txt : 
  - Before : -rw-r--r--
  - After : -r--r--r--
- notes.txt : 
  - Before : -rw-r--r--
  - After : -rw-r-----
-script.sh :
  - Before : -rw-r--r--
  - After : -rwxr-xr-x
- project :
  - Before : drwxr-xr-x (its default is 755)
  - After : drwxr-xr-x

  ## Commands Used
  - touch
  - vim/vi
  - ls -l
  - cat
  - view / vim -R
  - cat
  - head
  - tail
  - chmod
  - mkdir

  ## What I learned
  - Linux permission check order: Owner->Group->Others
  - Execute permission is must for run scripts
  - Two ways of change permission by chmod : Numeric (755,640,..) and flag (-w,+x,..)
  - File Security 
  
