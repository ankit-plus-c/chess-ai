# chess ai

A toy implementation of ~~neural network~~ normal chess.

<img width=600px src="https://raw.githubusercontent.com/geohot/twitchchess/master/screenshot.png" />

Can beat me at bullet, maybe rated 1200-1400. Search is 3-ply full with a 5-ply beam(x10).

Usage
-----

```
 pip3 install python-chess torch torchvision numpy flask
 # then...
 ./play.py   # runs webserver on localhost:5000
```

Implementation
-----

chess ai is a simple 1 look ahead neural network value function. The trained net is in nets/value.pth. It takes in a serialized board and outputs a range from -1 to 1. -1 means black is win, 1 means white is win.

Serialization
-----

We serialize the board into a 8x8x5 bitvector. See state.py for how.

Training Set
-----

The value function was trained on 5M board positions from http://www.kingbase-chess.net/

