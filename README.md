# cleanup-youtube-chat
Little user script to be used in TamperMonkey which just cleans up repeated messages in a rolling window from YouTube.

# How does it work
* Override window.fetch and catch all live_chat network requests
* Build up a dictionary of all messages stripping out any non-word characters (a-zA-Z0-9 + unicode)
* If a message appears again check how long it's been since it appeared
* If under a threshold of count + time, don't let the browser know the message existed
