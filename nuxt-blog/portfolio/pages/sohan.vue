<template>
  <div>
    <h1>This is Sohan Page.</h1>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Suscipit sint veritatis fugiat repudiandae, nobis voluptates. Magni, est accusamus, quidem repellendus nisi doloribus impedit cum ab ut adipisci vero dignissimos autem?
    </p>
    <hr>
    <div class="carousel">
      <div class="image-container">
        <img
          id="carouselImage"
          :src="getImagePath()"
          alt="Carousel Image"
          ref="zoomImage"
          @click="zoomImage"
        />
        <div class="info-container">
          <h2>{{ getTitle() }}</h2>
          <p><a :href="getGitHubLink()" target="_blank">GitHub Link</a></p>
          <p><a :href="getVideoLink()" target="_blank">Video Link</a></p>
          <p>Image Number: {{ currentIndex + 1 }}</p>
          <p>Description: {{ getDescription() }}</p>
        </div>
      </div>
      <button @click="prevImage">Previous</button>
      <button @click="nextImage">Next</button>
    </div>
  </div>
</template>

<script>
import mediumZoom from 'medium-zoom';

export default {
  data() {
    return {
      currentIndex: 0,
      images: [
        {
          src: 'cat-4.png',
          title: 'Cute Cat 1',
          githubLink: 'https://github.com/yourusername/project1',
          videoLink: 'https://www.youtube.com/watch?v=yourvideo1',
          description: 'This is the description for Cute Cat 1.',
        },
        {
          src: 'cat-5.png',
          title: 'Cute Cat 2',
          githubLink: 'https://github.com/yourusername/project2',
          videoLink: 'https://www.youtube.com/watch?v=yourvideo2',
          description: 'This is the description for Cute Cat 2.',
        },
        // Add more image objects as needed
      ],
      zoom: null,
    };
  },
  mounted() {
    // Initialize medium-zoom on the image
    this.zoom = mediumZoom(this.$refs.zoomImage, {
      margin: 24, // Adjust the zoomed-in margin as needed
    });
  },
  methods: {
    getImagePath() {
      return `/images/${this.images[this.currentIndex].src}`;
    },
    getTitle() {
      return this.images[this.currentIndex].title;
    },
    getGitHubLink() {
      return this.images[this.currentIndex].githubLink;
    },
    getVideoLink() {
      return this.images[this.currentIndex].videoLink;
    },
    getDescription() {
      return this.images[this.currentIndex].description;
    },
    prevImage() {
      this.currentIndex = (this.currentIndex - 1 + this.images.length) % this.images.length;
    },
    nextImage() {
      this.currentIndex = (this.currentIndex + 1) % this.images.length;
    },
    zoomImage() {
      this.zoom.show();
    },
  },
};
</script>

<style scoped>
.carousel {
  position: relative;
  max-width: 600px; /* Adjust the maximum width as needed */
  margin: auto;
}

.image-container {
  position: relative;
}

#carouselImage {
  width: 100%;
  height: auto;
  cursor: pointer;
}

button {
  background-color: #3498db;
  color: #fff;
  padding: 10px;
  border: none;
  cursor: pointer;
}

.info-container {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  background-color: rgba(52, 73, 94, 0.8);
  color: #fff;
  padding: 10px;
  text-align: center;
}

h2 {
  margin: 0;
}
/*npm install medium-zoom
npm run dev

*/
</style>
