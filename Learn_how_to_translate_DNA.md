Four tasks
1. Download DNA (`NM_207618.2`) as `dna.txt` and its corresponding protein seq as `protein.txt` from NCBI to computer

2. Import DNA into python

There are two ways to read a file in python
  - [Line by line](Wk1_basics.md#reading-and-writing-files)
  - Complete file at once
  ```
  # first make sure the pwd is correct
  inputfile = "dna.txt"
  f = open(inputfile,"r")
  seq = f.read() # read entire file
  ```
3. Create algorithm that translates DNA using provided translation table
4. Check if the DNA translation matches the downloaded protein string

