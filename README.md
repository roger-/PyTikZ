# Description

PyTikZ is a simple Python to [TikZ](http://en.wikipedia.org/wiki/PGF/TikZ) translator. It's probably good enough to
generate some basic diagrams (and importantly avoid TeX loops), but you may need to
edit the output due to missing functionality and bugs.

Some basic documentation can be found in tikz.py

## Examples

The output of the following code should be more-or-less equivalent to [this](http://www.texample.net/tikz/examples/glider/):

```python
import tikz

pic = tikz.Picture('thick')

circle_size = 0.42
circle_pos = [(0, 0), (1, 0), (2, 0), (2, 1), (1, 2)]

with pic.path('draw') as draw:
    draw.at(0 + 0j).grid_to(3 + 3j)

with pic.path('fill') as fill:
    for pos in circle_pos:
        fill.at(pos).circle(circle_size)

print pic.make()
```

# License

All of the code contained here is licensed by the GNU General Public License v3.

Copyright (C) 2014 by Roger <https://github.com/roger->