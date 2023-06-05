![Logo](https://github.com/ajotanc/wled-matrix-converter/assets/47322034/3f03c754-3624-45b7-9a77-21b661562f3d)

# WLED 2D Matrix Converter
It is an application that converts any image into code in JSON WLED format to 2D Matrix standards, currently it has only been tested on the 2D Matrix panel, but soon I will post news for the serpentine version.

### Features
- Converts any type of image
- Option on tape address format
- Result output option
- Choice of brightness intensity
- Convert transparent pixels to chosen color
- Convert animated GIFs
- Resize image
- Select image direct from **[WLED-IP]/edit** or **upload**
- Can save, simulate, copy or download generated code

## INTERFACE VERSION
### Download
**Right-Click** [[Interface]](https://raw.githubusercontent.com/ajotanc/wled-matrix-converter/main/interface.htm) and select save to your local computer.

### Tutorial
Showing usability in the interface version in an easy, simple and intuitive way.

https://github.com/ajotanc/wled-matrix-converter/assets/47322034/20ad60d1-3b01-42b6-9937-4dda3862a3a4

## INLINE VERSION
### Download
**Right-Click** [[Inline]](https://raw.githubusercontent.com/ajotanc/wled-matrix-converter/main/inline.htm) and select save to your local computer.

### Example of what the URL looks like
```
  GET http://[WLED-IP]/inline.htm?id=0&output=ha&brightness=255&pre_segment=individual&device=pixel_art_controller_001&unique_id=pixel_art_controller_001a&friendly_name=PixelArt&hostname=[WLED-IP]&color=3CCFFE5&image=33.png&download=true&simulate=false
```
## CURL GENERATE WLED JSON
```bash
# Local image upload
# Remember to change the \path\image.png path to the desired image path.
curl -X POST -F "file=@\path\image.png" "https://ajota.vercel.app/api/wled/image?id=0&output=json&brightness=255&pre_segment=individual&hostname=10.0.0.41&color=CCFFE5"

# External image upload
curl -X POST -F "file=@-;filename=image.png" "https://ajota.vercel.app/api/wled/image?id=0&output=curl&brightness=255&pre_segment=individual&hostname=10.0.0.41&color=CCFFE5" < <(curl -s "https://img.freepik.com/premium-vector/lightning-pixel-art-gaming-item-game-pixel-lightning_158677-585.jpg")
# OR
curl -o /tmp/image.png -s "https://img.freepik.com/premium-vector/lightning-pixel-art-gaming-item-game-pixel-lightning_158677-585.jpg" && curl -X POST -F "file=@/tmp/image.png" "https://ajota.vercel.app/api/wled/image?id=0&output=curl&brightness=255&pre_segment=individual&hostname=10.0.0.41&color=3CCFFE5"
```

#### Description of parameters
| Parameters | Type | Description | Default | Required |
| ---------- | ---- | ------- | ----------- | -------- | 
| `id` | `integer` | Segment id | **0** | ✅
| `output` or `o` | `string` | Output type, options [json, curl, ha] | **json** | ✅
| `brightness` or `bri` | `integer` | Brightness of the LEDs | **128** | ✅
| `pre_segment` or `ps` | `string` | Address type, options [individual ["FFFFFF"], index [0, "FFFFFF"], range [0, 5, "FFFFFF"] | **individual** | ✅
| `hostname` or `hn` | `string` | WLED IP | - | ✅
| `width` or `w` | `number` | Resize image width | **16** | ⬜️
| `height` or `h` | `number` | Resize image height | **16** | ⬜️
| `device` or `d` | `string` | Device name, mandatory if the output is "ha" | - | ⬜️
| `unique_id` or `uid` | `string` | Unique device id, required if output is "ha" | - | ⬜️
| `friendly_name` or `fn` | `string` | Friendly name of the device, mandatory if the output is "ha" | - | ⬜️
| `color` or `c` | `string` | If the image contains a transparent background, you can change it to a desired color by passing the color in the HEX pattern | - | ⬜️
| `animation` or `anim` | `boolean` | If true, it will return the WLED JSON according to the number of frames in the GIF image. | **false** | ⬜️
| `amount` or `amt` | `number` | Number of frames contained in the GIF image, if the **animation** parameter is **true** | **0** | ⬜️
| `delay` or `dl` | `number` | Delay seconds between executions **curl**, optional and only for **output** curl | **2** | ⬜️
| `image` | `string` | Image that will be converted to JSON WLED, required only if using the **inline** version | - | ✅
| `file` | `boolean` | If true, it will download the file according to the output, required only if using the **inline** version | **false** | ⬜️
| `simulate` | `boolean` | If true and output is "json" then simulate JSON WLED, required only if using the **inline** version | **false** | ⬜️

## Utility
Function and performance tests were carried out if you use a 32x32 panel or larger, the ideal `pre_segment` parameter is **range**

[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://choosealicense.com/licenses/mit/)
