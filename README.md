# Non-English_AutoSpellFix

This repository contains my solution to a coding assignment on automatic spell correction for words that are non-English in origin (e.g., Hindi, Marathi) but written using the English alphabet.
The goal is to design a  efficient spell-correction algorithm that can handle spelling errors in large text files and map each misspelled word to the most likely correct form.

----------------------------------------------------------------------------------------

🧠 Problem Statement
Given:
A dictionary file reference.txt containing ~5,000 correct words (e.g., Aam, Bandega, Pattagurya, Ram, etc.), one word per line.

The task is to:
Automatically correct each word in input.txt using the words in reference.txt as the vocabulary.
Handle many realistic error types (insertions, deletions, substitutions, transpositions, repeated letters, etc.).
Produce an output file with both the original (possibly incorrect) word and the corrected word.

Example error–correction pairs:
ROM → Ram, 
RAAM → Ram, 
Aum → Aam, 
RAUM → Ram

✨ Output:
The program produces a corrected output file, for example corrections.csv, with the following format:
File_Error - Corrected ->
Aum	 - Aam, 
ROM  - Ram, 
RAAM -  Ram

-----------------------------------------------------------------------------------------

🧮 My Implementation uses:
Edit distance (Levenshtein distance) to measure how similar a misspelled word is to each dictionary word.
Optional normalization steps such as:
Lowercasing,
Collapsing repeated characters (e.g., raaam → ram),
Removing leading/trailing spaces or punctuation.

For each word in input.txt, the script:
Computes its similarity to all words in reference.txt.
Chooses the closest matching word within a maximum distance threshold.

------------------------------------------------------------------------------------------

⚙️ The repository contains two versions of the spell correction script:
- Auto_spell_1.py
    Designed for small-scale correction tasks. It uses only input.txt and generates corrected words directly without requiring a reference dictionary.
- Auto_spell_2.py
    Intended for large-scale correction (up to ~5,000+ words). It requires both input.txt (misspelled input words) and reference.txt (dictionary of valid words) to produce accurate corrections.

🛠️ Tech Stack
Language: Python 3.x
Libraries:
re, csv, pathlib (standard library)

------------------------------------------------------------------------------------------
