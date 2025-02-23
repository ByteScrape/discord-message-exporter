# Discord Message Exporter

This Python script allows you to export all messages from a specific Discord channel to a JSON file. It uses the Discord API and handles rate limits, network errors, and graceful shutdowns to ensure reliable data extraction.

## Features

* Exports all messages from a specified Discord channel.
* Saves messages in JSON format for easy analysis or backup.
* Handles Discord API rate limits to avoid getting blocked.
* Gracefully handles network errors and resumes fetching messages.
* Supports graceful shutdown with signal handling to save progress.
* Includes logging for debugging and monitoring.

## Requirements

* Python 3.7 or higher
* The following Python packages:
    * aiohttp
    * emoji
    * colorama

You can install these packages using `pip install -r requirements.txt`.

## Usage

1. **Obtain your Discord authorization token.** You can find instructions on how to do this online.
2. **Get the channel ID of the Discord channel you want to export.** You can find this by right-clicking on the channel in Discord and selecting "Copy ID".
3. **Configure the script.** Open the `main.py` file and update the following variables:
    * `CHANNEL_ID`: Set this to the channel ID you obtained in step 2.
    * `AUTH_TOKEN`: Set this to your Discord authorization token.
    * `output_file`: (Optional) Change this to customize the output file name.
    * `save_interval`: (Optional) Adjust the frequency of saving messages to the JSON file.
4. **Run the script.** Execute the script using `python main.py`.
5. **Monitor the progress.** The script will log its progress to the console. You can also check the `exports` folder for the exported JSON file.

## Graceful Shutdown

The script supports graceful shutdown using Ctrl+C or other interrupt signals. When an interrupt is detected, the script will attempt to save the current progress to the JSON file before exiting.

## Logging

The script uses a custom logger to provide detailed information about its progress and any errors encountered. The log messages are color-coded for easier readability in the console. You can configure the logging level and output in the `utils/logger.py` file.

## Contributing

Contributions are welcome! If you find any bugs or have suggestions for improvements, please feel free to open an issue or submit a pull request.
