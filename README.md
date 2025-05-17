# Ex05 Image Carousel
## Date:17-05-25

## AIM
To create a Image Carousel using React 

## ALGORITHM
### STEP 1 Initial Setup:
Input: A list of images to display in the carousel.

Output: A component displaying the images with navigation controls (e.g., next/previous buttons).

### Step 2 State Management:
Use a state variable (currentIndex) to track the index of the current image displayed.

The carousel starts with the first image, so initialize currentIndex to 0.

### Step 3 Navigation Controls:
Next Image: When the "Next" button is clicked, increment currentIndex.

If currentIndex is at the end of the image list (last image), loop back to the first image using modulo:
currentIndex = (currentIndex + 1) % images.length;

Previous Image: When the "Previous" button is clicked, decrement currentIndex.

If currentIndex is at the beginning (first image), loop back to the last image:
currentIndex = (currentIndex - 1 + images.length) % images.length;

### Step 4 Displaying the Image:
The currentIndex determines which image is displayed.

Using the currentIndex, display the corresponding image from the images list.

### Step 5 Auto-Rotation:
Set an interval to automatically change the image after a set amount of time (e.g., 3 seconds).

Use setInterval to call the nextImage() function at regular intervals.

Clean up the interval when the component unmounts using clearInterval to prevent memory leaks.

## PROGRAM

## jsx
```
import React, { useState } from 'react';
import './App.css';

const images = [
  '/vk.webp',
  '/vk18.webp'
];

function App() {
  const [index, setIndex] = useState(0);

  const showPrevious = () => {
    setIndex((prevIndex) => (prevIndex === 0 ? images.length - 1 : prevIndex - 1));
  };

  const showNext = () => {
    setIndex((prevIndex) => (prevIndex === images.length - 1 ? 0 : prevIndex + 1));
  };

  return (
    <div className="app">
      <h1 className="title">God Of Clutch</h1>
      <div className="carousel">
        <img src={images[index]} alt="cricket" className="carousel-image" />
      </div>
      <div className="buttons">
        <button onClick={showPrevious}>Previous</button>
        <button onClick={showNext}>Next</button>
      </div>
    </div>
  );
}

export default App;
```
## css
```
.app {
  text-align: center;
  padding: 20px;
  min-height: 100vh;
  background: linear-gradient(to right, #1e3c72, #2a5298); /* Updated gradient */
  color: #fff;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}
.carousel {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 400px;
  margin-bottom: 20px;
}
.carousel-image {
  width: 600px;
  height: 400px;
  object-fit: cover;
  border-radius: 16px;
  box-shadow: 0 6px 15px rgba(0, 0, 0, 0.4);
  transition: transform 0.3s ease-in-out;
}
.carousel-image:hover {
  transform: scale(1.03);
}

/* Navigation buttons */
.buttons {
  display: flex;
  justify-content: center;
  gap: 20px;
  margin-top: 20px;
}

.buttons button {
  padding: 12px 24px;
  font-size: 16px;
  background-color: #ff9f43;
  border: none;
  border-radius: 10px;
  color: white;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.buttons button:hover {
  background-color: #e07b24;
}
```
## OUTPUT

![WhatsApp Image 2025-05-17 at 14 09 05_adef862f](https://github.com/user-attachments/assets/97ebe614-4551-4536-9e64-b35c13bd54dc)
![WhatsApp Image 2025-05-17 at 14 09 05_a7e2094b](https://github.com/user-attachments/assets/048cc4fa-8511-4fdc-8c5b-d6b88c2296b0)

## RESULT
The program for creating Image Carousel using React is executed successfully.
