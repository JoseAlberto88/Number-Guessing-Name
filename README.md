# Number Guessing Game 🎯  
A command‑line number guessing game built in **Bash** with a **PostgreSQL** backend, created as part of the freeCodeCamp Relational Database Certification.  
The game stores user profiles, tracks game history, and records personal best scores.

---

## 🛠️ Tech Stack

<p align="left">
  <img src="https://img.shields.io/badge/Bash-121011?style=for-the-badge&logo=gnu-bash&logoColor=white" />
  <img src="https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white" />
  <img src="https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white" />
  <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" />
  <img src="https://img.shields.io/badge/freeCodeCamp-0A0A23?style=for-the-badge&logo=freecodecamp&logoColor=white" />
</p>

---

## 📌 Project Overview  
This project implements an interactive guessing game where users try to guess a randomly generated number between **1 and 1000**.  
Each user has a persistent profile stored in a PostgreSQL database, allowing the game to track:

- Total games played  
- Best (fewest guesses) game  
- Username history (up to 22 characters)

The game provides feedback after each guess and validates input to ensure only integers are accepted.

---

## 🗄️ Database Structure  
The project uses a single database: **`number_guess`**

### **Table: `users`**
| Column        | Type        | Description |
|---------------|-------------|-------------|
| user_id       | SERIAL PK   | Unique user identifier |
| username      | VARCHAR(22) | Player's username |
| games_played  | INT         | Total games played |
| best_game     | INT         | Fewest guesses needed to win |

---

## 🎮 Game Features  
- Prompts the user for a username  
- Greets returning players with their stats  
- Generates a random number between **1 and 1000**  
- Validates integer input  
- Provides hints:
  - *“It's higher than that, guess again:”*  
  - *“It's lower than that, guess again:”*  
- Records game results in the database  
- Updates best score automatically  
- Clean, simple CLI experience

---

## 🧩 How It Works  
1. User enters a username  
2. Script checks if the user exists in the database  
3. A secret number is generated  
4. User guesses until correct  
5. Script tracks number of attempts  
6. Results are saved to the database  
7. User receives a final message showing:
   - Number of guesses  
   - The secret number  
   - A congratulatory note  

---

## 🚀 Run the Game

```bash
./number_guess.sh
```
## 📦 Database Backup

### Export your database:

```bash
pg_dump -cC --inserts -U freecodecamp number_guess > number_guess.sql
```

### Restore your database:
```bash
psql -U postgres < number_guess.sql
```

## 📝 Git Requirements

This project includes:

- A dedicated folder: `number_guessing_game/`
- At least **five commits**
- Commit messages following:
  - `feat:`
  - `fix:`
  - `refactor:`
  - `chore:`
  - `test:`
- Clean working tree on the **main** branch
- No uncommitted changes at submission time

## 🎉 Acknowledgments

Built as part of the **freeCodeCamp Relational Database Certification**.  
Thanks to the freeCodeCamp team for providing an excellent learning platform.

## 📚 License

This project is open‑source and available under the MIT License.
