<template>
  <div class="section mt-5 ">
    <div class="column text-center ">
      <h2>Instructions</h2>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Laudantium sint odit rem eaque tempore nostrum odio
        fugiat ipsum laborum. At similique voluptates nostrum architecto excepturi laboriosam repellat amet quos
        perferendis.</p>
    </div>
    <div class="column text-center ">
      <h2>Task</h2>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Delectus necessitatibus totam laudantium minus veritatis
        ad, ea ipsum sequi atque, odit, quasi ducimus illo consectetur. Voluptas mollitia error id odio quae?</p>
    </div>
    <div class="column text-center">
      <h2>Answer</h2>
      <div class="input-section">
        <textarea placeholder="Enter JavaScript code..."></textarea>
        <div class="bhover">
          <button v-on:click="submitCode">Submit</button>

        </div>

      </div>
    </div>



  </div>
</template>

<script>
export default {
  name: 'HelloWorld',

  methods: {
    submitCode() {
      alert("Submit Your JavaScript code:");
    },

  }

};
</script>
<style scoped>
.section {
  display: flex;
  margin-top: 80px !important;
}

.column {
  background-color: #f1dfdf;
  padding: 20px;
  margin: 10px;
  box-sizing: border-box;
  height: 550px;
  width: 380px;
  border-radius: 12px;
}

.column p {
  margin-top: 20px;
}

.column h2 {
  color: rgb(21, 4, 99);
}

.input-section {
  margin-top: 20px;
}

textarea {
  width: 100%;
  padding: 8px 0 0 8px;
  height: 400px;
  resize: none;
  border-radius: 4px;
  border-color: lightslategrey;
}

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

@media only screen and (max-width: 300px) {
  .column {
    display: block;
  }
}
</style>

