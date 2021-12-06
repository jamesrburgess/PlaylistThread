# PlaylistThread
sketch for making a thread that runs a process stoppable in a controlled way. It sub-classes threading.Thread and overrides run(). So you create one of these things and then call start() on it. Now any thread can call play(), stop_playing() and exit().

This sketch needs a media player program to run like omxPlaylist.py. It beleives the way to stop that program from playing audio is to send it a SIGINT (so this probaly won't work on windows) 

# test
The __main__ test needs to know where the omxPlaylist.py program is. When you run it, it creates a PlaylistThread call "pl", starts it and then drops you in a REPL:

    --> python playt.py
    Python 3.7.6 (v3.7.6:43364a7ae0, Dec 18 2019, 14:18:50) 
    [Clang 6.0 (clang-600.0.57)] on darwin
    Type "help", "copyright", "credits" or "license" for more information.
    (InteractiveConsole)
    >>> pl.play('/Users/jrb/sounds/animals')
    >>> pl.play('/Users/jrb/sounds/boats')
    >>> pl.stop_playing()
    >>> ^D
    now exiting InteractiveConsole...
    --> 
