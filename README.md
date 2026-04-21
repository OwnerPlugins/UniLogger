<h1 align="center">🎉 My Universal Logger Plugin</h1>

![Visitors](https://komarev.com/ghpvc/?username=Belfagor2005&label=Repository%20Views&color=blueviolet)
[![Enigma2](https://img.shields.io/badge/Enigma2-Plugin-ff6600.svg)](https://www.enigma2.net)
[![Python](https://img.shields.io/badge/Python-3-blue.svg)](https://www.python.org)
[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
[![Donate](https://img.shields.io/badge/_-Donate-red.svg?logo=githubsponsors&labelColor=555555&style=for-the-badge)](https://ko-fi.com/lululla)

<div align="center">
**A simple and flexible Python logging utility designed for plugins. Keep your plugin logs organized, easy to read, and automatically handled!**
</div>



---

## 🚀 Features

- Custom logger for each plugin
- Automatic log file creation and rotation
- Clear logs on startup (optional)
- Debug, info, warning, error messages
- Full exception tracking
- Display messages directly to users

---

## 🛠 Installation

Simply copy the logger module (`your_logger_module.py`) into your plugin folder.
No extra dependencies needed — just pure Python magic! ✨

---

## 📝 Quick Start

```python
if __name__ == "__main__":
    # Example of module usage
    logger = get_logger(
        log_path="/tmp/my_plugin_logs",
        plugin_name="my_awesome_plugin",
        clear_on_start=True,
        max_size_mb=2
    )

    logger.debug("This is a debug message")
    logger.info("This is an informational message")
    logger.warning("Warning!")
    logger.error("Error!")

    try:
        raise ValueError("Sample error")
    except Exception as e:
        logger.exception("Caught exception: %s", e)
````

---

## 🔧 Using the Logger in Your Plugins

1. **Import the module**

```python
from your_logger_module import get_logger
```

2. **Create a logger instance**

```python
class MyPlugin:
    def __init__(self):
        self.logger = get_logger(
            log_path="/tmp/my_plugin_logs",
            plugin_name="MyPlugin",
            clear_on_start=True,
            max_size_mb=1
        )
```

3. **Log messages in your functions**

```python
def my_function(self):
    self.logger.debug("Starting function")
    self.logger.info("Operation completed")

    try:
        # code that may raise errors
        pass
    except Exception as e:
        self.logger.exception("Error during operation: %s", e)
```

4. **Show messages to users**

```python
def show_info(self, session):
    self.logger.show_message(session, "Operation completed successfully!")
```

---

## 📂 Where Logs Go

Logs are saved in the path you specify (`log_path`).
Each plugin can have its own log folder and file size limit for easy rotation.

---

## ⚡ License

MIT License — free to use and modify!
by Lululla


