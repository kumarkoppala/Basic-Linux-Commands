## Read command
* **Interactive input:** Prompt the user for input during script execution.
* **Reading files line by line:** Process text files efficiently.
* **Assigning multiple variables:** Split input into separate variables.
* **Silent input:** Hide typed input (useful for passwords).
* **Timeouts:** Limit waiting time for user input.
``` bash
read name            # Read a single word into variable 'name'
read a b c           # Read three space-separated values into a, b, c
read -p "Age: " age  # Prompt inline and store input in 'age'
read -s pass         # Read input silently (e.g., password)
read -t 5 choice     # Wait max 5 seconds for input
read -a arr          # Read space-separated values into array 'arr'
while read line; do echo $line; done < file.txt  # Read file line by line
read -n1 ch          # Read a single character into 'ch'
read -n1 -p "Key: " k  # Prompt and read one character
read -n5 str         # Read exactly 5 characters into 'str'
read -a words        # Read space-separated words into array 'words'
for w in $line; do echo $w; done  # Print words one by one from a line
while read -n1 c; do echo $c; done < file.txt  # Read file char by char
while read -a arr; do echo ${arr[0]}; done < file.txt  # Read file word by word
IFS=, read a b c <<< "one,two,three"   # Split into a=one, b=two, c=three
IFS=, read -a arr <<< "apple,banana,cherry"  # Store words into array arr
while IFS=, read x y; do echo "$x | $y"; done < file.csv  # Read CSV line by line
IFS=, read first second <<< "$(echo 'foo,bar')"  # Assign foo and bar
IFS=, tells read to treat commas as separators.

<<< is a here‑string (feeds a string directly into read).

With -a, you can grab all comma‑separated values into an array.

In loops, this trick is perfect for parsing CSV files.
```

-n1 → grabs one character at a time.

-n5 → grabs five characters at once.

-a → splits input into words stored in an array.

Loops (while/for) let you process text character‑by‑character or word‑by‑word from files or streams.


