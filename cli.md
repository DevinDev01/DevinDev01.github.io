# CLI
---

## Options <!-- {docsify-ignore} -->
| Option | Type | Default | Description |
| ------ | ---- | ------- | ----------- |
| `--in/-i` | `string` | `main.lua` | lua script file to run. |
| `--out/-o` | `string` | `out` | output file name provided in the code as `OUTPUT_FILE`. |
| `--width/-w` | `int` | `0` | width in pixels of the canvas provided in the code as `WIDTH`. |
| `--height/-h` | `int` | `0` | height in pixels of the canvas provided in the code as `HEIGHT`. |
| `--size/-s` | `int` | `256` | when provided overrides width and height to whatever value is set. |
| `--scale` | `float` | `1.0` | scales the outputted file up or down while retaining the aspect ratio and size of drawn elements. |
| `--clear` | `bool` | `False` | for use when exporting GIFS when you would like previous frames to layer instead of clearing the canvas each time. | 
| `--data/-d` | `string/int/float/bool` |  | allows a way to dynamically give the lua code user provided variables. |

## Examples <!-- {docsify-ignore} -->
#### Basic Usage

This will run `main.lua` and use the default values shown above.
```bash
./imagine
```

### Other Usages

This will run `code.lua` and set the options for the width, height and output name
```bash
./imagine --in code.lua --width 64 --height 64 --out my_image
```

Similar to previous but the output will be scaled up by 2 so you will be using a 64px by 64px canvas but the ouput will be 128px by 128px this provides many benifits the main one being faster processing time.
```bash
./imagine --in code.lua --width 64 --height 64 --out my_image --scale 2
```

This will run using the default values but in the lua code you will have access to variables `D_RADIUS` and `D_VALUE` which are auto converted to there respective types to use however you would like.
```bash
./imagine --data radius=20 --data value=false
```
