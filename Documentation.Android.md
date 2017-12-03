# Telegram Bot for Android
It is a light weight framework to manage your Telegram Bot
## How to Download
You can download the library using **Gradle** or **Maven**
#### Gradle
```groovy
compile 'com.ajts.library.telegrambot:telegrambotlibrary:1.0.0'
```
#### Maven
```groovy
<dependency>
  <groupId>com.ajts.library.telegrambot</groupId>
  <artifactId>telegrambotlibrary</artifactId>
  <version>1.0.0</version>
  <type>pom</type>
</dependency>
```
## How to Use
### Telegram Bot Initialization
```java
Telegram telegram = new Telegram("<bot-token>");
```
### Authorizing Telegram Bot
```java
telegram.getMe(new TelegramCallback<GetMe>() {
	@Override
	public void onResponse(Call call, final GetMe getMe) {
		Log.v("response.body()", getMe.isOk() + "");
	}

	@Override
	public void onFailure(Call call, Exception e) {

	}
});
```
### Send Text Message
```java
telegram.sendMessage("<Channel-Name or Chat-ID>", "TelegramBotLibrary", new TelegramCallback<Message>() {
	@Override
	public void onResponse(Call call, Message response) {
		Log.v("response.body()", response.isOk() + "");
	}

	@Override
	public void onFailure(Call call, Exception e) {

	}
});
```
### Send Text Message with Html and Markdown
#### Html
```java
telegram.sendMessage("<Channel-Name or Chat-ID>",
	"<i>TelegramBotLibrary</i>",
	Telegram.ParseMode.HTML,
	new TelegramCallback<Message>() {
		@Override
		public void onResponse(Call call, Message response) {
			Toast.makeText(MainActivity.this, response.isOk() + "", Toast.LENGTH_SHORT).show();
		}

		@Override
		public void onFailure(Call call, Exception e) {

		}
	});
```
#### Markdown
```java
telegram.sendMessage("<Channel-Name or Chat-ID>",
	"*TelegramBotLibrary*",
	Telegram.ParseMode.Markdown,
	new TelegramCallback<Message>() {
		@Override
		public void onResponse(Call call, Message response) {
			Toast.makeText(MainActivity.this, response.isOk() + "", Toast.LENGTH_SHORT).show();
		}

		@Override
		public void onFailure(Call call, Exception e) {

		}
	});
```
### Send Photo
```java
telegram.sendPhoto("<Channel-Name or Chat-ID>",
	TelegramMediaType.Image.png,
	new File(imagePickedPath),
	"telegram photo",
	new TelegramCallback<Message>() {
		@Override
		public void onResponse(Call call, Message response) {
			Toast.makeText(MainActivity.this, response.isOk() + "", Toast.LENGTH_SHORT).show();
		}

		@Override
		public void onFailure(Call call, Exception e) {

		}
	});
```
### Send Video
```java
telegram.sendVideo("<Channel-Name or Chat-ID>",
	TelegramMediaType.Video.mp4,
	new File(videoPickedPath),
	"telegram video",
	new TelegramCallback<Message>() {
		@Override
		public void onResponse(Call call, Message response) {
			Toast.makeText(MainActivity.this, response.isOk() + "", Toast.LENGTH_SHORT).show();
		}

		@Override
		public void onFailure(Call call, Exception e) {

		}
	});
```
### Send Audio
```java
telegram.sendAudio("<Channel-Name or Chat-ID>",
	TelegramMediaType.Audio.mp3,
	new File(audioPickedPath),
	"telegram audio",
	new TelegramCallback<Message>() {
		@Override
		public void onResponse(Call call, Message response) {
			Toast.makeText(MainActivity.this, response.isOk() + "", Toast.LENGTH_SHORT).show();
		}

		@Override
		public void onFailure(Call call, Exception e) {

		}
	});
```
### Send Document
```java
telegram.sendDocument("<Channel-Name or Chat-ID>",
	TelegramMediaType.Document.file,
	new File(documentPickedPath),
	"telegram document",
	new TelegramCallback<Message>() {
		@Override
		public void onResponse(Call call, Message response) {
			Toast.makeText(MainActivity.this, response.isOk() + "", Toast.LENGTH_SHORT).show();
		}

		@Override
		public void onFailure(Call call, Exception e) {

		}
	});
```
### Send Location
```java
telegram.sendLocation("<Channel-Name or Chat-ID>",
	"<Latitude>",
	"<Longitude>",
	new TelegramCallback<Message>() {
		@Override
		public void onResponse(Call call, Message response) {
			Toast.makeText(MainActivity.this, response.isOk() + "", Toast.LENGTH_SHORT).show();
		}

		@Override
		public void onFailure(Call call, Exception e) {

		}
	});
```
### Send Venue
```java
telegram.sendVenue("<Channel-Name or Chat-ID>",
	"<Latitude>",
	"<Longitude>",
	"<Address>",
	"<Country>",
	new TelegramCallback<Message>() {
		@Override
		public void onResponse(Call call, Message response) {
			Toast.makeText(MainActivity.this, response.isOk() + "", Toast.LENGTH_SHORT).show();
		}

		@Override
		public void onFailure(Call call, Exception e) {

		}
	});
```
