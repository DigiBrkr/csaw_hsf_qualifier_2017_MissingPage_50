# Missing Page
50 points
> This was also included in Herbert's drive, maybe we can get more from it? It's the same pdf as in Mount Image, but we've reuploaded for your convenience.
## Solving it

After extensive research, I figured out that to solve the challenge I needed a tool called `pdf-extract` https://github.com/CrossRef/pdfextract. It's part of the package `origami-pdf`. To install, we type `# apt install origami-pdf`. Once we have it installed, we type `# pdfextract mypasswords.pdf`. That will generate a folder called `mypasswords.dump`. Then we `cd` into the folder: `# cd mypasswords.dump/`.
Then type `# ls` and you should see this:
```
# ls
attachments  fonts  images  scripts  streams
```
Now we `cd` into the `streams` folder:
`# cd streams/`.
Then we see a bunch of `.dmp` files:

```
ls
stream_14.dmp  stream_18.dmp  stream_22.dmp  stream_6.dmp  stream_9.dmp

```
The numbers might be different for you, I'm not sure.
Now we do a `grep` search for the word `flag`: `# grep "flag" *`.

This gives us the following:
`stream_18.dmp:[(flag{di)4(d_)-2(u_)-2(100)3(k_unde)-4(r_the_keyb)-2(oard?})] TJ`.
I know it looks rough, but if we go through it carefully we can clean it up to the following:
`(flag{did_u_100k_under_the_keyboard?}`
Knowing a little `l337 5p34k` might help with this!  
And that gives us our flag:
`(flag{did_u_100k_under_the_keyboard?}`


