# Advanced Targeted Password Wordlist Generator

## Project Purpose
This tool is designed to generate **highly focused, personalized password wordlists** using **real-world data** such as names, DOBs, pet names, and other personal identifiers. Instead of brute-forcing with millions of generic entries, this tool generates **fewer but higher-probability passwords** for **red teaming, dictionary attacks, and credential stuffing.**

It simulates how real users build passwords, making it effective for penetration testing and social engineering engagements.

## Core Use Cases
- Dictionary attacks (Hydra, Medusa, Burp Suite, etc.)
- CTF challenges
- Internal pentest engagements
- Credential reuse testing
- Red team password profiling

## Usage

### Manual Input
```bash
python3 main.py --manual
```
In manual mode, the tool will prompt you for various personal details one by one, such as names, dates, pet names, and other preferences. You can leave any field blank to skip it. After the structured inputs, you will be prompted for additional keywords, tags, and keyboard patterns. Type 'done' and press Enter to finish each of these sections.

### Profile Input
Create a JSON file (e.g., `profile.json`) with relevant data. The `profile_loader.py` now includes validation for required keys (`name`, `dob`, `pet`, `keywords`).
```json
{
  "first_name": "john",
  "middle_name": "",
  "last_name": "doe",
  "nickname": "james",
  "dob": "14071994",
  "birth_year": "1994",
  "pet_name": "max",
  "partner_name": "nisha",
  "favorite_color": "blue",
  "favorite_team": "barca",
  "school_name": "stjohn",
  "special_words": ["007", "786", "admin"]
}
```
Then run:
```bash
python3 main.py --profile profile.json
```

### Options
- `-m`, `--manual`: Enable manual input mode.
- `-p`, `--profile`: Path to a JSON profile for data loading.
- `-o`, `--output`: Output file name (default: `wordlist.txt`).
- `--min-length`: Minimum password length (default: 6).
- `--max-length`: Maximum password length (default: 16).
