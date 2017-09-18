My problem with formatters (like prettier and refmt) is truncating width aggressively. They sacrifice readability, and for what?

Find "something" prop in:

lsdkjf sldjfsldkjfsldkjf sdlkfj slfjdlfkjsldkfj something sldkjflksjd flskdjf sdlskjf

vs
lsdkjf
lsdkjfslkdjf
lsdkjfsds
sldkf
something
sdlkfjsdf
sldkjf
sldkjffsldkjf

Now nest in other components. Bullet view requires a scroll, but still faster to find prop than reading left-right.

---

prettier cares about line length. This is the one feature I hate. Also, it is fast.