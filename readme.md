#pushover nvgt.
##what is this?
	Pushover is a notification service that simplifies sending push notifications to both your desktop and mobile devices.
	This class wraps most of pushover's API, including sending notifications, handling notification receipts, and more.
##getting started
	To get started, visit https://pushover.net/api and obtain an application token.
	You must supply your token when initializing instances of your pushover classes, like this.
	```
	#include"pushover.nvgt" //include your script.
	//your main function.
	void main() {
	string app_token = "your_app_token";
	pushover p(app_token);
	//obtain your device's user ID and set it, like so.
	p.set_user_key("key");
	p.notify("This is a test");
	}
	```
#handling urgent priority notifications
	##If you send a notification with priority set to 2 (the highest priority), your notification will keep being pushed to your devices until the notification is acknowledged by one of your devices. By default, this class sends urgent notifications every 30 seconds for 5 minutes. You only need to send out the notification once, pushover will handle the rest for you.
	You must call pushover::pull in your application's main loop. You can only check receipts every 5 seconds, however it is perfectly valid to call this as many times as you wish, the class will handle each notification for you.
	You can optionally set a callback to handle these notification receipts, see test.nvgt for an example on doing this.
	Please note that once your notification is acknowledged, the callback will not be triggered multiple times.
##important notes!
	This code is still in beta and not everything has been tested.
	If you have any improvements to this class, feel free to open a pull request.