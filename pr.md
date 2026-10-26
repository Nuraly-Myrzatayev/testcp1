<!--
Checkpoint 1: your diagnosis. Keep the four headings. After each fix, fill in its block:
  Step:      the name of the step where you saw the fault, as the Actions page shows it
  Log line:  ONE line copied from that step's log, between the backticks, exactly as shown
  Changed:   the file you changed, and what you changed, in a sentence of your own
English, please. Russian or Kazakh is fine if you are stuck for a word.
-->

### 1. The pipeline runs
- Step: Run the tests
- Log line: `./scripts/tests.sh: No such file or directory`
- Changed: ci.yml changed the name to test.sh as tests.sh do not exist

### 2. The pipeline tells the truth
- Step: Run the tests
- Log line: `FAILED (failures=1)`
- Changed: test.sh changed the status to assign rather than not being set and the program to always return true 

### 3. The service keeps the contract
- Step: Run the tests
- Log line: `AssertionError: Tuples differ: (200, '2') != (200, '3')`
- Changed: server.py for some reason it changed the actual length so i set it to not do that

### 4. The image builds
- Step: Build the image
- Log line: `"/source": not found`
- Changed: Dockerfile tried to copy non existing directory "/source" so i changed it to more probable "/src"
