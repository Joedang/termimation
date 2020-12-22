# Termimation (terminal animation)
Display a short video or GIF in the terminal.
You can [check out a video demonstration here.](https://imgur.com/a/Tup3RIp)

## Usage
`termimation input.gif` will convert the GIF into a series of images (in `/tmp/`), 
convert those into an array of text, and display the elements of that array successively to play the animation.
This will have the same *average* frame rate as the input file.
`Ctrl-C` can be used to abort the animation.

I think `jp2a` gives prettier results out of the box, but both `jp2a` and `img2txt` can be thoroughly configured. 
`ffmpeg` is probably a little bit faster and more versatile than `imagemagick`.

## Warnings
That this draws each frame starting at row 0, column 0 in your terminal in a kind of brute-force way.
So, it will clobber up to the last screen-full of your scrollback buffer.

This loads the entire ASCII-art-ified animation into memory.
You should only use this with short and/or low-frame-rate files.
If you try to display long/high-FPS video, you'll run out of memory pretty quickly.

## Dependencies
- bash (obviously)
- coreutils
- ffmpeg (or imagemagick as a fallback)
- jp2a (or libcaca as a fallback) 
- bc
