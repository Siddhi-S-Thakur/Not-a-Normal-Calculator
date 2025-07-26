# Not-a-Normal-Calculator
This is a simple Python-based calculator that accepts user input in the form of basic arithmetic expressions (e.g., 8 + 8), calculates the result, and stores the full expression along with the answer (e.g., 8 + 8 = 16) in a text file. Users can view their calculation history or clear it anytime using simple commands

A variable is created to store the filename where the history of all calculations will be saved.

The show_history() function opens this file in read mode and stores its content (line by line) in a variable called lines. If the file is empty, a message is displayed saying that no history is found.

The clear_history() function opens the file in write mode, which clears all the existing contents of the file — this effectively resets the history.

The save_to_history() function opens the file in append mode, which means new data will be added to the end of the file without deleting what's already there. It writes the expression entered by the user along with the calculated result.

The result is converted to a string before writing because the write() function in Python only accepts string data. If we try to directly write a number (like an int or float), Python will raise a TypeError. So, we use str(result) to ensure that the result is in the correct format for writing to the file.

The calculate() function first takes the user’s input and splits the expression (e.g., 8 + 8) into three parts using the split() function. These parts are stored in a list called parts[], where:

parts[0] is the first number,
parts[1] is the operator (e.g., +, -, *, /`),
parts[2] is the second number.

Then, the function checks which operator was used by comparing op with each of the four valid arithmetic operators. Based on the operator, it performs the corresponding calculation.

After the result is calculated, the code checks if the result is a whole number (i.e., no decimal part). If it is, the result is **converted to an integer** using int(result) — this is done purely for better display formatting (e.g., showing 16 instead of 16.0 when the result is a whole number).

Finally, the result is printed and saved to the history file using the save_to_history() function.



