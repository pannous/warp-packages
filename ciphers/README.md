# ciphers

The classic hand ciphers and Morse code. Letters keep their case; spaces, digits and punctuation pass unchanged.

```warp
use ciphers
print caesar("Hello, World!", 3)              # Khoor, Zruog!
print vigenere("attack at dawn", "lemon")     # lxfopv ef rnhr
print to_morse("SOS")                         # ... --- ...
```

Words: `caesar`, `uncaesar`, `rot13`, `atbash`, `vigenere`, `unvigenere`, `to_morse`, `from_morse`.

Try it: `warp example.warp` in this folder.
