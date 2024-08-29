# AnsI/O

[![pypi](https://img.shields.io/pypi/v/ansio.svg)](http://pypi.org/project/ansio)
[![python](https://img.shields.io/pypi/pyversions/ansio.svg)](http://pypi.org/project/ansio)
[![license](https://img.shields.io/pypi/l/ansio.svg)](http://pypi.org/project/ansio)
[![pytest](https://github.com/nineteendo/ansio/actions/workflows/pytest.yml/badge.svg)](https://github.com/nineteendo/ansio/actions/workflows/pytest.yml)
[![downloads](https://img.shields.io/pypi/dm/ansio.svg)](http://pypi.org/project/ansio)

AnsI/O module for ansi input &amp; output

## Example usage

### Keyboard input

```python
from ansio import application_keypad, mouse_input, raw_input
from ansio.input import InputEvent, get_input_event

with raw_input, application_keypad, mouse_input:
    while True:
        event: InputEvent = get_input_event()
        print(event.pressed, repr(event.shortcut))
```

Example output:

```none
True 'alt+shift+a'
True 'ctrl+a'
True 'tab'
True 'shift+up'
True 'a'
True 'primary_click'
False 'primary_click'
True 'ctrl+primary_click'
False 'ctrl+primary_click'
```

### Colored output

```python
from ansio import colored_output
from ansio.colors import blue_bg, invert, italic, yellow

with colored_output:
    print(f'Print in {yellow(blue_bg("color"))} and with {italic(invert("styles"))}')
```

Example output:

![](assets/colored_output.png)
