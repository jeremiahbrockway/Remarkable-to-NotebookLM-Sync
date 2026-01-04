# Remarkable-to-NotebookLM-Sync
A Google Apps Script to automate the sync between reMarkable and NotebookLM. It pulls handwriting-to-text exports from Gmail and appends them to specific Google Docs daily. Perfect for building a live, AI-searchable research base from handwritten notes and To-Do lists.

# What this script does
Automate the pipeline between your reMarkable 2 tablet and Google NotebookLM. This Google Apps Script monitors your Gmail for "Convert to Text" exports, extracts the content, and appends it to designated Master Google Docs overnight.

# The Workflow
  1. On reMarkable: Finish your notes and use the Convert to text and send feature.
  2. In Transit: The script identifies the notebook type via "Fuzzy" subject matching.
  3. In Google Drive: Your Master Google Docs are updated with a date-stamped entry.
  4. In NotebookLM: Tap the "Sync" button to instantly ground your AI in your latest handwritten thoughts.  

# Setup Instructions
# 1. Prepare Google Docs
  Create two Google Docs in your Drive (e.g., in a folder called Remarkable - AI Foundry Updates).
    • Note Updates Doc
    • To-Do Updates Doc
  Copy the File ID from the URL of each doc (the long string between /d/ and /edit).
  
# 2. Install the Script
  1. Go to script.google.com and create a New Project.
  2. Paste the code from sync.gs in this repo.
  3. Replace the NOTES_DOC_ID and TODO_DOC_ID variables with your actual IDs.
  4. Tap the Save icon and then Run to authorize the script permissions.

# 3. Set the Automation Trigger
  1. In the Apps Script editor, click the Triggers (alarm clock) icon on the left.
  2. Click + Add Trigger.
  3. Choose syncEverything as the function to run.
  4. Set the event source to Time-driven -> Day timer.
  5. Select a window (e.g., Midnight to 1am).

# Usage Tips
  • Consistency is Key: Ensure your notebook names on the reMarkable include the keywords Note Updates or To Do Updates.
  • Text Format: Always use the "Text in email" body option when sending from your tablet.
  • NotebookLM Sync: NotebookLM does not auto-refresh. Open your notebook and click the circular Sync icon next to your sources to ingest the previous night's updates.

# License
MIT License - Feel free to use and modify!
How to use this on GitHub:
  1. Create a new file in your repo named README.md.
  2. Copy and paste the text above into it.
  3. Create a second file named sync.gs and paste your final working code into that.
