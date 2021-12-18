# LearnGraphicURL
some graphic knowledge url

## Texture Format
### image to differ between what the shader sees and what is stored in the image

The Image Format of the image may be different from the format specified to the image binding function and in the shader. Values read and written are converted in the following way, assuming that the formats are compatible.

The term "source format" represents the image format of whatever the source of the operation is. Similarly, the "destination format" is the image format of whatever the destination of the operation is. Therefore:

Read operation:
Source format: The image's actual format.
Dest format: The format specified by the image binding function glBindImageTexture (which must match the format declared in the shader qualifier).
Write operation:
Source format: The format specified by the image binding function glBindImageTexture.
Dest format: The image's actual format.
All operations, whether read or write, function as though they were copying data from/to images with those formats. The first step of a write operation would be taking the value provided by the shader and writing that into a texture in the source image format. Then the format conversion takes place, copying the value into the destination. Similarly, the last step of read operations is reading from the destination image into the value in the shader.
 see: https://www.khronos.org/opengl/wiki/Image_Load_Store
