# Pillow

## Description
- **Main Functionality**: Python Imaging Library (PIL) fork, providing image processing capabilities.
- **Use in Planetology**: Used for processing and analyzing images obtained from planetary missions and observations.

## Technical Requirements
- **Version**: Pillow 10.0 or higher.

## Links and Resources
- **Official Documentation**: [Pillow Documentation](https://pillow.readthedocs.io/en/stable/)

## Code snippet
```python
from PIL import Image, ImageDraw, ImageFont, ImageFilter

# Create a new image (background color: white)
width, height = 400, 300
image = Image.new('RGB', (width, height), 'white')

# Initialize the drawing object
draw = ImageDraw.Draw(image)

# Draw an ellipse (color: blue)
ellipse_bbox = (50, 50, 350, 250)
draw.ellipse(ellipse_bbox, outline='blue', width=3)

# Draw a rectangle (color: red)
rectangle_bbox = (100, 75, 300, 225)
draw.rectangle(rectangle_bbox, outline='red', width=3)

# Draw a line (color: green)
line_start = (0, 0)
line_end = (400, 300)
draw.line([line_start, line_end], fill='green', width=3)

# Add text to the image (color: black)
text = "Hello, Pillow!"
font = ImageFont.load_default()
text_position = (120, 130)
draw.text(text_position, text, font=font, fill='black')

# Apply a filter (blur)
blurred_image = image.filter(ImageFilter.BLUR)

# Save the resulting image
blurred_image.save('output_image.png')

# Display the image
blurred_image.show()

