# Tortise

### What is Tortise
Tortise is a (very) simple, distributed, decentralized twitter which runs over tor.
It is designed to be a good basis for learning more about how to build systems
on top of privacy protecting technology like Tor.


### Instructions
0. Make sure you have the latest python installed, using a tool like brew
0. Clone this repository to your home directory
1. Install Tor Browser: https://www.torproject.org/
2. Add the following lines to your torrc file.

    ```
    HiddenServiceDir /Users/<YOUR USERNAME>/tortise/priv 
    HiddenServicePort 80 127.0.0.1:8083
    ```
    Hints:
      * You'll need to customize the directory paths to wherever you cloned this repo!
      * The priv/ subfolder will automatically be created
      * My torrc is located at: /Applications/TorBrowser.app/TorBrowser/Data/Tor/torrc
      * Still Need help? https://www.torproject.org/docs/tor-hidden-service.html.en has more detailed instructions

    Fun Fact: the -rc suffix doesn't really stand for anything useful, but you can think of it as resource configuration.
3. (Re)Start TorBrowser.
4. in src/, run `python run.py`, and leave it running. This is your server.
    You may need some dependencies:
    `pip install PySocks`
    `pip install tornado`
5. check priv/hostname to see your onion address (keep key in priv private)
6. Paste the address into the Tor Browser to connect.
7. visit /peer on your website to put your friends domains (ie, http://<hostname>/ in and send/recieve messages

8. CHALLENGE EXERCISES:
  1. Make your peers persistent: that is, make it so that you don't need to reconnect every time
  2. Allow People to post messages with a username...
    * Make that username a keypair!
  3. Make a nicer user interface 
  4. Clear out old messages
  5. Make it so that only you can post to your server
