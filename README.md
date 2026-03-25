A collection of lightweight Conky configurations and Python scripts to display your Google Calendar events directly on your Linux desktop. This repository contains two versions: a Minimalist layout and an Enhanced layout with advanced features like recurrence support and color-coded grouping.
📋 Table of Contents

    Prerequisites

    Installation

    Configuration

    The Variants

        1. Event-Calendar (Minimalist)

        2. Event-Calendar-Alt (Enhanced)

    Usage

🛠 Prerequisites

Both versions require a Python virtual environment to manage dependencies:

    Create the environment:
    python3 -m venv ~/.gcal_env

    Install dependencies:
    ~/.gcal_env/bin/pip install requests icalendar python-dateutil

🚀 Installation

    Clone this repository to your Conky configuration directory:
    git clone <your-repo-url> ~/.conky/

    Make the Python scripts executable:
    chmod +x ~/.conky/Event-Calendar/parse_ical.py
    chmod +x ~/.conky/Event-Calendar-Alt/parse_ical.py

⚙️ Configuration

To display your calendar, you must provide your private iCal link:

    Go to Google Calendar Settings.

    Under "Settings for my calendars," select your calendar.

    Scroll down to Integrate calendar.

    Copy the Secret address in iCal format.

    Paste this URL into the ICAL_URL variable inside the parse_ical.py script of your chosen version.

🎨 The Variants
1. Event-Calendar (Minimalist)

A clean, simple list of upcoming events.

    Features: Displays the next 5 events with date and time.

    Visuals: Uses "Google Blue" (color1) and supports rounded backgrounds via a Lua hook.

    Best for: Users who want a low-profile overlay that doesn't distract from the desktop.


2. Event-Calendar-Alt (Enhanced)

A feature-rich dashboard with intelligent grouping and formatting.

    Features:

        Recurrence Support: Correctly handles recurring events.

        Smart Grouping: Categorizes events into "TODAY", "TOMORROW", or specific days of the week.

        Metadata: Displays event locations with a ⌖ icon.

        Visuals: High-contrast palette using JetBrainsMono Nerd Font.

        Robustness: Includes specific error handling for timeouts, network loss, and bad data.

    Best for: Users who need a detailed look at their upcoming month at a glance.

🖥 Usage

To run a version, navigate to the directory and launch Conky pointing to the specific config file:

For Minimalist:
conky -c ~/.conky/Event-Calendar/calendar.conkyrc

For Enhanced:
conky -c ~/.conky/Event-Calendar-Alt/calendar.conkyrc
