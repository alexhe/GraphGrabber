# GraphGrabber

Used to grab full-resolution images of IDA graphs.

Released under MIT license.

## Dependencies

1. [Sark](https://github.com/tmr232/Sark)
1. [Pillow](https://python-pillow.org/)

## Prerequisites
Disable graph animation in IDA's options (`Options -> General -> Graph -> General -> Enable Graph Animations`).

## Usage

### As Script
Execute via `File -> Script File...`

### As Plugin
Either use [Sark's plugin loader](https://github.com/tmr232/Sark/blob/master/plugins/plugin_loader.py) to load the plugin,
or remove these lines from the end of the file:
```python
if __name__ == '__main__':
    if is_script_file():
        capture_graph()
```

Once the plugin is loaded, use <kbd>Ctrl</kbd><kbd>Alt</kbd><kbd>G</kbd> to grab a screenshot.


## Known Issues
1. The tool does not support gradient backgrounds.  
   **Workaround:**
    1. Use a single-color background
    1. Remove graph shadows (in IDA's options)
    1. Capture the graph image
    1. Replace the background in an image editor
