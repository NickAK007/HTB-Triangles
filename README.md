The project is all about a HTB(Hack The Box challenge) called Triangles, which is described as "Three vertices.Two csv files.One solution"
The challenge in essence is to pinpoint a ‘flag’ using the location of three vertices and their distances from previously defined points on a ‘grid’ of 100x100 cells filled with a variery of case sensitive characters, numbers, and symbols.
The challenge provides us with four files, two csv and two python.
grid.csv file consists of a 100x100 grid of various alphaneumeric characters and symbols from which we identify and extract the flag for the challenge.
out.csv consists of the distances from each flag element to three 'vertices' on the grid, followed by the inter-vertices distances, which help us uniquely identify each triplet on the grid, followed by the flag element.
In this challenge, the characters of flag are hidden in the grid.csv file, using the triangulate script. The triangulate script takes the original coordinates of each character of the flag, uses a random offset of -7 to 7 to modify the coordinates and creates three such coordinates.
After creating these coordinates, it takes the values of these coordinates from the grid.csv and provides us two parts of information:
 1) distances of these offset characters from the original character.
 2) distances among these offset characters.
The output of the flag coordinates modified by this triangulate script are given to us in out.csv file.
Using these two bits of information, we can design a python script in such a way that:
First we can find the offset character coordinates by using the second part of the given information - distance among the offset characters to find these offset characters, the offset characters' coordinates will satisfy all three distance conditions.
After finding the offset characters, we can get the original character coordinates by using the part-1 information, where we can verify if a character is having same distance value from offset characters as provided in out.csv
Tools used: MS Excel, VS Code, Jupyter Notebook.
Solution:
By solving the puzzle involed in the grid.csv using the distances from out.csv, we can run the triangles script to arrive at the solution to the challenge box, which is a 22 character long flag.
Outcomes:
Data Analysis: Analyzing and interpreting the data from two CSV files (grid.csv and out.csv) and integrating it with the logic provided in the Python scripts (secret.py and triangulate.py).
Geometric Analysis: Using the logic behind grid.csv and out.csv to geometrically pinpoint the offset vertices on the grid and further using these to identify the original flag element.
Decoding a Flag: The main goal of the challenge is to figure out how to decipher a grid's secret flag, as it is a CTF(capture the flag) challenge, following the guidelines provided by the Python scripts.
The project "Triangles" encourages critical thinking and problem-solving skills in a stimulating and demanding environment, along with testing technical proficiency in data analysis, cryptography, and programming.
