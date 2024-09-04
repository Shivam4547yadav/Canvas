# Canvas
In this we have created an canvas which works when we scroll mouse by using HTML and JS.
.
.
.
.
.
.
.
For frames you can take any video cut it into frames and then plased it into a file then ->
    const canvas = document.querySelector("canvas");
      const context = canvas.getContext("2d");

      const frames = {
        currentIndex: 0,
        maxIndex: 382,       //set the number of frames you have
      };

      let imagesLoaded = 0;
      const images = [];
      // let expectedImages = frames.maxIndex + 1; // account for 0-based indexing

      function preloadImage() {
        for (var i = 1; i <= frames.maxIndex; i++) {
          const imageUrl = `./canvas2/frame_${i.toString().padStart(4,"0")}.jpeg`;      //check the file path and image type.

          const img = new Image();
          img.src = imageUrl;
          img.onload = () => {
            imagesLoaded++;
            if (imagesLoaded === frames.maxIndex) {
              loadImage(frames.currentIndex);
              startAnimation();
            }
          }
          images.push(img);
        }
      }
