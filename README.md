# MWAD_EX05_image-carousel-in-react
## Date:30/10/25

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
## APP.JSX:
```
import React, { useState } from 'react';
import './App.css';

const images = [
  'RCB.PNG',
  'IND.PNG'
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
      <h1 className="title">Cricket🏏</h1>
      <div className="carousel">
        <img src={images[index]} alt="Aniverse" className="carousel-image" />
      </div>
      <div className="buttons">
        <button onClick={showPrevious}>Previous</button>
        <button onClick={showNext}>Next</button>
      </div>

      {/* Footer */}
      <div className="footer">
        &copy; NITHISH R  ||  212223040135
       </div>
    </div>
  );
}

export default App;
```

## APP.CSS:
```
body {
  margin: 0;
  padding: 0;
  font-family: 'Poppins', sans-serif;
  background: linear-gradient(to bottom right, #6da4ea, #7531bd);
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

.app {
  background: rgb(243, 234, 234);
  border-radius: 20px;
  padding: 40px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.15);
  text-align: center;
  width: 700px;
  max-width: 90%;
}

.title {
  font-size: 2.5rem;
  color: #4c1d95;
  font-weight: 700;
  margin-bottom: 30px;
}

.carousel {
  position: relative;
  width: 100%;
  height: 400px;
  overflow: hidden;
  border-radius: 15px;
  margin-bottom: 20px;
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.2);
}

.carousel-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 15px;
  transition: opacity 0.6s ease-in-out, transform 0.3s ease-in-out;
}

.buttons {
  display: flex;
  justify-content: center;
  gap: 20px;
  margin-bottom: 25px;
}

button {
  background-color: #6e12f8;
  color: white;
  border: none;
  border-radius: 8px;
  padding: 12px 28px;
  font-size: 1rem;
  cursor: pointer;
  transition: all 0.3s ease-in-out;
}

button:hover {
  background-color: #6d28d9;
  transform: scale(1.05);
}

.footer {
  font-size: 14px;
  color: #555;
  border-top: 1px solid #ddd;
  padding-top: 15px;
  margin-top: 20px;
}



```

## OUTPUT

<img width="1919" height="1079" alt="Screenshot 2025-11-19 211222" src="https://github.com/user-attachments/assets/e3c15779-2c8d-43f3-a84e-d50c918776c4" />

<img width="1915" height="1079" alt="Screenshot 2025-11-19 211206" src="https://github.com/user-attachments/assets/398a5fc4-22f1-4ed3-91a0-288ad1453d3b" />



## RESULT
The program for creating Image Carousel using React is executed successfully.
