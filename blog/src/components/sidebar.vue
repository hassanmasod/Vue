<template>
    <div :class="['sidebar', { expanded: isExpanded }]">
        <i @click="toggleSidebar" :class="arrow" class="fa-solid fa-bars"></i>
    
        <div class="logo-container">
          <div class="imgText search-icon">
            <i v-on:click="toggleSidebar" class="fa-solid fa-magnifying-glass"></i>
            <span v-if="isExpanded">
              <form action="#">
                <input
                  type="search"
                  class="search-data"
                  placeholder="Search"
                /></form
            ></span>
          </div>
          

          <div class="imgText">
            <i v-on:click="toggleSidebar" class="fa fa-home"></i>
            <span v-if="isExpanded">Home</span>
          </div>
          <div class="imgText">
            <i @click="toggleSidebar" class="fa fa-wikipedia-w"></i>
            <span v-if="isExpanded">Wikipedia</span>
          </div>
          <div class="imgText">
            <i @click="toggleSidebar" class="fa fa-amazon"></i>
            <span v-if="isExpanded">Amazon</span>
          </div>
          <div class="imgText">
            <i @click="toggleSidebar" class="fa fa-user-secret"></i>
            <span v-if="isExpanded">User</span>
          </div>

          <div class="imgText">
            <i v-on:click="toggleSidebar" class="fa fa-video-camera"></i>
            <span v-if="isExpanded">
                <div id="app" class="web-camera-container">
                    <div class="camera-button">
                      <button type="button" class="button is-rounded"
                        :class="{ 'is-primary': !isCameraOpen, 'is-danger': isCameraOpen }" @click="toggleCamera">
                        <span v-if="!isCameraOpen">Open Camera</span>
                        <span v-else>Close Camera</span>
                      </button>
                    </div>
            
                    <div v-if="isPhotoTaken && isCameraOpen" class="camera-download">
                      <a id="downloadPhoto" download="my-photo.jpg" class="button" role="button" @click="downloadImage">
                        Download
                      </a>
                    </div>
                  </div>
            </span>
            
          </div>

        </div>
      </div>
    
</template>

<script>
export default{
    name : 'SIDEBAR',
    data() {
    return {
      isExpanded: false,
      isCameraOpen: false,
      isLoading: false,
    };
  },
  methods: {
    toggleSidebar() {
      this.isExpanded = !this.isExpanded;
    },


    toggleCamera() {
      if (this.isCameraOpen) {
        this.isCameraOpen = false;
        this.stopCameraStream();
      } else {
        this.isCameraOpen = true;
        this.createCameraElement();
      }
    },
    createCameraElement() {
      this.isLoading = true;

      const constraints = (window.constraints = {
        audio: false,
        video: true
      });


      navigator.mediaDevices
        .getUserMedia(constraints)
        .then(stream => {
          this.isLoading = false;
          this.$refs.camera.srcObject = stream;
        })

    },

    stopCameraStream() {
      let tracks = this.$refs.camera.srcObject.getTracks();

      tracks.forEach(track => {
        track.stop();
      })
    }

  
  },
};

</script>


<style scoped>
button {
    display: block;
    margin-top: 10px;
    padding: 8px 16px;
    background-color: rgb(21, 4, 99);
    color: white;
    border: none;
    cursor: pointer;
    border-radius: 4px;
  
  }
  button:hover {
    background-color: rgb(234, 0, 255);
  }
.sidebar {
  border-radius:18px ;
  
    margin-top: 90px;
    border-top: 1px solid white;
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 50px; /* Initial width of the sidebar */
    background-color: #f1dfdf;
    padding: 10px;
    color: rgb(21, 4, 99);
    transition: width 0.3s;
    height: 34rem;
  }
  .imgText {
    margin: 0 12px;
    display: flex;
    align-items: center;
  }
  .search-icon {
    display: none;
  }
  .fa-solid:hover {
    color: rgb(234, 0, 255);
  }
  .fa-video-camera:hover {
    color: rgb(234, 0, 255);
  }
  .fa-home:hover {
    color: rgb(234, 0, 255);
  }
  .fa-wikipedia-w:hover {
    color: rgb(234, 0, 255);
  }
  .fa-amazon:hover {
    color: rgb(234, 0, 255);
  }
  .fa-user-secret:hover {
    color: rgb(234, 0, 255);
  }
  .expanded {
    width: 150px; /* Expanded width of the sidebar */
  }
  
  .logo-container {
    display: flex;
    flex-direction: column;
  }
  
  button {
    display: block;
    width: 100%;
    padding: 5px;
    margin-top: 10px;
  }
  .fa-bars {
    font-size: 28px;
    margin: 8px 0 20px 0;
    cursor: pointer;
    color: rgb(21, 4, 99);
  }
  .fa {
    font-size: 28px;
    margin: 16px 0 20px 0;
    cursor: pointer;
  }
  span {
    margin-left: 12px;
  }
  form {
    display: flex;
    height: 34px;
    background: #171c24;
    border-radius: 4px;
    border: 1px solid rgba(155, 155, 155, 0.2);
  }
  
  form .search-data {
    height: 100%;
    width: 180px;
    padding: 0 10px;
    color: #fff;
    font-weight: 500;
    background: none;
    border: none;
    font-size: 17px;
    outline: none;
  }
  
  
  
  @media only screen and (max-width: 200px) {
    .search-icon {
      display: none;
      
      
    }
    .fa-solid {
      font-size: 18px;
      margin: 20px 0 20px 0;
      
    }

  }
  

</style>