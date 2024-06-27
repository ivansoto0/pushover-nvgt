# pushover.nvgt

## What is this?
Pushover is a notification service that simplifies sending push notifications to both your desktop and mobile devices. This class wraps most of Pushover's API, including sending notifications, handling notification receipts, and more.

## Getting Started
To get started, visit [Pushover API](https://pushover.net/api) and obtain an application token.
You must supply your token when initializing instances of your pushover classes, like this:

```nvgt
#include "pushover.nvgt" // include your script.

// your main function
void main() {
	string app_token = "your_app_token";
	pushover p(app_token);
	
	// obtain your device's user ID and set it, like so
	p.set_user_key("key");
	p.notify("This is a test");
}
