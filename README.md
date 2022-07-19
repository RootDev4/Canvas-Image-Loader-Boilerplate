# Canvas Image Loader Boilerplate
Image loader for drawing images on JavaScript canvas.

## Image loading function
```javascript
const loadImage = imageSrc => {
    return new Promise((resolve, reject) => {
        try {
            const image = new Image()
            image.src = imageSrc
            image.onload = () => resolve(image)
        } catch (error) {
            reject(error)
        }
    })
}
```

## Load and draw image
Create canvas
```javascript
const canvas = document.querySelector('canvas')
const context = canvas.getContext('2d')
```
Load image from local source
```javascript
// Load and draw image
const image = await loadImage('./player.png')
context.drawImage(image, 200, 50, image.width, image.height)
```
Load image from URL
```javascript
const image = await loadImage('https://example.com/yourimage.png')
context.drawImage(image, 200, 50, image.width, image.height)

