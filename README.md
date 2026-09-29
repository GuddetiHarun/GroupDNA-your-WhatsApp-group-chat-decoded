GroupDNA — your WhatsApp group chat, decoded

Spotify Wrapped, but for your friend group. GroupDNA reads a raw WhatsApp chat export 
and turns it into a formatted analytics report — busiest hours, favourite words, 
response speed, silent streaks, and a personality archetype for every member — 
built using only core Python and NumPy.

Output:

<img width="632" height="985" alt="Screenshot 2026-09-29 192108" src="https://github.com/user-attachments/assets/060b6bf9-a628-46f9-b7c4-c6ad6e80585c" />



What this project does:

- Breaks down WhatsApp `.txt` export file line-by-line, dealing with system messages, 
  missing-media, deleted messages, and multi-line messages
- Generates group statistics in general: message statistics, period, per-person statistics
- Detects the most active day and hour
- Creates a 6×24 NumPy heatmap of activity of individuals for every hour of the day
- Extracts the top 10 most frequently used words in the group (using a custom set of stop-words)
- Calculates the average time to respond and the longest period without messages for each individual
- Labels each person as belonging to exactly one personality type (Spammer, Night Owl, 
  Group Mom, Storyteller, Drama Queen, Ghost, Comedian, Question Master) using rules 
  evaluated on the basis of their own messages
- Extra archetype: the 9th archetype invented by myself is Placement Pandit
  (a person whose messages contain only placements, deadlines, and exam-related stuff)

Constraints:

This project was built under a strict "fundamentals-only" rule, to prove the 
report can be built without heavier libraries.

Allowed: core Python (loops, conditionals, functions, f-strings, string 
methods), lists/dicts/sets/tuples, NumPy, `open()` file reading, and 
`datetime.strptime` / `timedelta` for timestamp parsing.

Not used: pandas, matplotlib/seaborn/plotly, `collections.Counter` or 
`defaultdict`, regex (`re`), and any pre-built chat-analysis or ML library.

Dataset:

`hostel_bois.txt` - Synthetic (fabricated) WhatsApp chat export of a 6-member hostel chat
over a period of 60 days (01 April 2024 to 30 May 2024) as part of the GroupDNA project 
briefing from The Unlox Academy. This consists of 3,174 genuine messages along with system messages, 
media omissions, and deleted messages.

How to run it:

1. Clone or download this repository.
2. Open `GroupDNA_<Harun>_<21921>.ipynb` in Google Colab (or Jupyter).
3. Upload `hostel_bois.txt` to the same session (in Colab: drag it into the 
   file panel on the left, so it lands at `/content/hostel_bois.txt`).
4. Run all cells (`Runtime → Run all`). No extra installs are needed — only 
   NumPy, which Colab has pre-installed.

