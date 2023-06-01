
# Título do Projeto

Uma breve descrição sobre o que esse projeto faz e para quem ele é



## Documentação

#### Returns the JSON LED

```http
  GET http://[WLED-IP]/commands.htm?id=0&output=json&brightness=256&pre_segment=range&device=pixel_art_controller_001&unique_id=pixel_art_controller_001a&friendly_name=PixelArt&hostname=[WLED-IP]&color=%23CCFFE5&image=33.png&download=true&simulate=false
```

| Parameters | Type | Default | Description | Required |
| ---------- | ---- | ------- | ----------- | -------- | 
| `id` | `integer` | 0 | Segment id | - [x] 
| `output` | `string` | **Obrigatório**. A chave da sua API | |
| `brightness` | `integer` | **Obrigatório**. A chave da sua API | |
| `pre_segment` | `string` | **Obrigatório**. A chave da sua API | |
| `hostname` | `string` | **Obrigatório**. A chave da sua API | |
| `color` | `string` | **Obrigatório**. A chave da sua API | |
| `image` | `string` | **Obrigatório**. A chave da sua API | |
| `device` | `string` | **Obrigatório**. A chave da sua API | |
| `unique_id` | `string` | **Obrigatório**. A chave da sua API | |
| `friendly_name` | `string` | **Obrigatório**. A chave da sua API | |
| `file` | `boolean` | **Obrigatório**. A chave da sua API | |
| `simulate` | `boolean` | **Obrigatório**. A chave da sua API | |

# matrix-converter
Image converter for WLED presets and playlists JSON 

Soon I will add the documentation, in the meantime follow a tutorial below:
 
https://github.com/ajotanc/pixelart-converter/assets/47322034/76bec6c3-7143-4453-815e-cc73fdc3a137

