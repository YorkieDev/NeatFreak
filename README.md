# NeatFreak: The Ultimate Download Organizer

NeatFreak is a powerful and user-friendly application designed to keep your downloads folder organized automatically. With its intuitive interface and smart categorization system, NeatFreak makes file management a breeze. Note, this has only been tested on MacOS, use at your own discretion. No warranty, support etc is given or implied. 

## Features

- **Automatic File Organization**: Sorts files into appropriate folders based on their types.
- **Custom Categories**: Easily define your own categories and file type mappings.
- **Real-time Monitoring**: Option to watch the downloads folder and organize new files as they arrive.
- **Undo Functionality**: Easily revert the last organization action if needed.
- **Detailed Reports**: Generate reports on the organization process, including file types and sizes.
- **Plugin Support**: Extend functionality with custom plugins.
- **Modern UI**: Clean and intuitive user interface for easy interaction.

## Installation

1. Ensure you have Python 3.7 or later installed on your system.

2. Clone this repository or download the source code:
   ```
   git clone https://github.com/YorkieDev/neatfreak.git
   cd neatfreak
   ```

3. Install the required dependencies:
   ```
   pip install pydantic watchdog PyYAML
   ```

4. Create a `config.yaml` file in the same directory as the script, or in one of the following locations:
   - `~/.config/neatfreak/config.yaml`
   - `/etc/neatfreak/config.yaml`

   Example `config.yaml`:
   ```yaml
   directory: "/path/to/your/downloads"
   extension_map:
     ".pdf": "Documents"
     ".jpg": "Images"
     ".mp3": "Music"
   exclusions:
     - ".tmp"
     - ".part"
   max_threads: 4
   days_to_keep_record: 7
   ```

5. (Optional) Create a `plugins` directory in the same location as the script if you want to use plugins.

## Usage

Run the application by executing:

```
python neatfreak.py
```

The NeatFreak window will appear with the following options:

- **Organize Now**: Start the organization process immediately.
- **Undo Last Organization**: Revert the last organization action.
- **Start Watching**: Begin monitoring the downloads folder for new files.
- **Stop Watching**: Stop the monitoring process.
- **Generate Report**: Create a report of the organization actions.
- **Exit**: Close the application.

## Customization

### Config File

You can customize NeatFreak's behavior by modifying the `config.yaml` file:

- `directory`: The path to the downloads folder you want to organize.
- `extension_map`: Custom mappings of file extensions to category folders.
- `exclusions`: List of file extensions to ignore during organization.
- `max_threads`: Number of threads to use for file processing (default is 4).
- `days_to_keep_record`: Number of days to remember organized files (default is 7).

### Plugins

To extend NeatFreak's functionality, you can create custom plugins. Place your plugin files in the `plugins` directory. Each plugin should define a `Plugin` class with a `process` method.

## Contributing

Contributions to NeatFreak are welcome! Please feel free to submit pull requests, report bugs, or suggest features.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Thanks to all contributors who have helped shape NeatFreak.
- Special thanks to the developers of PyYAML, Watchdog, and Pydantic for their excellent libraries.

Enjoy your newly organized downloads folder with NeatFreak!
