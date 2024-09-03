# Discord Rich Presence Script

This script uses the `pypresence` library to display a custom Discord Rich Presence status update for your server. It allows you to show a large image, text details, and interactive buttons that link to external resources, such as your Discord server.

## Features

- Displays a large image and custom text on your Discord profile.
- Periodically updates details and state information.
- Supports up to two customizable buttons linking to external URLs.

## Requirements

- Python 3.x
- `pypresence` library

## Installation

1. Clone this repository:

    ```bash
    git clone https://github.com/userlaws/Discord-Rich-Presence-Script.git
    ```

2. Install the required Python packages:

    ```bash
    pip install pypresence
    ```

## Usage

1. Replace the `client_id` with your application's client ID from the Discord Developer Portal.
2. Customize the `large_image`, `details`, `state`, and `buttons` as desired.
3. Run the script:

    ```bash
    python status.py
    ```

## Example Script

Here's a sample script to get you started:

```python
from pypresence import Presence
import time

# Initialize the Discord Rich Presence
client_id = "your_client_id_here"  # Replace with your client ID
RPC = Presence(client_id)
RPC.connect()

# Time when the status started
start_time = int(time.time())

# Update the Discord status in an infinite loop
while True:
    RPC.update(
        large_image="your_asset_name",  # Replace with your image asset name
        large_text="Your Large Image Text",  # Text displayed when hovering over the large image
        details="Join our community!",  # Main detail text
        state="Having fun!",  # Secondary state text
        start=start_time,  # Start time for the status
        buttons=[
            {"label": "Join Discord", "url": "https://discord.gg/your_invite_code"}  # Replace with your URL
        ]
    )
    # Update every 60 seconds
    time.sleep(60)
```

## Customization

- **client_id**: Your application's client ID from the Discord Developer Portal.
- **large_image**: The name of your image asset uploaded to Discord's Rich Presence dashboard.
- **details** and **state**: Customize the text that appears below your username.
- **buttons**: Configure up to two buttons with labels and URLs.

## Contributing

Feel free to submit a pull request or open an issue to suggest improvements or report bugs.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

