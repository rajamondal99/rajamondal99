Close your eyes and copy the code and paste it.

```
import io
import PIL.Image as Image
import base64

byt = "Your byte code"

file_name = 'raja.png'
file_path = f"/home/insabhi/Desktop/{file_name}"

decoded_bytes = base64.b64decode(byt)
img = Image.open(io.BytesIO(decoded_bytes))
img.save(file_path)

```
