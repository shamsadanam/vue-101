<script setup>
import { ref } from "vue";
const showModal = ref(false);
const newNote = ref("");
</script>

<template>
  <main class="notes-page">
    <div class="notes-heading">
      <h1>Notes</h1>
      <button @click="showModal = true" class="add-note">Add</button>
    </div>
    <div v-if="showModal" class="overlay">
      <div class="note-input-area">
        <textarea
          v-model="newNote"
          name="note-input"
          id=""
          cols="30"
          rows="10"
        ></textarea>
        <button class="submit">Submit</button>
        <button class="close" @click="showModal = false">Close</button>
      </div>
    </div>
    <div class="notes-container">
      <div class="notes">
        <h4>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Odio, enim.
        </h4>
      </div>
      <div class="notes">
        <h4>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Odio, enim.
        </h4>
      </div>
      <div class="notes">
        <h4>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Odio, enim.
        </h4>
      </div>
      <div class="notes">
        <h4>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Odio, enim.
        </h4>
      </div>
    </div>
  </main>
</template>

<style scoped>
.notes-page {
  position: relative;
  max-width: 1024px;
  margin: 0 auto;
}
.notes-heading {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.notes-container {
  margin-top: 10px;
  display: flex;
  flex-wrap: wrap;
  gap: 1.5em;
}
.notes {
  background-color: aquamarine;
  width: 175px;
  height: 175px;
  padding: 10px 20px;
  border-radius: 15px;
}

.add-note {
  background-color: black;
  color: #fff;
  padding: 5px 15px;
  border-radius: 15px;
}

.add-note:hover {
  cursor: pointer;
}

.overlay {
  width: 600px;
  height: 300px;

  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  z-index: 9;
  display: inline-block;
  background-color: rgba(0, 0, 0, 0.75);
  border-radius: 20px;
}

.note-input-area {
  display: flex;
  flex-direction: column;
  padding: 20px;
  gap: 1em;
}
.submit,
.close {
  border-radius: 20px;
  padding: 7px;
}
.submit {
  border: none;
  background-color: rgb(150, 233, 150);
}

.close {
  border: none;
  background-color: rgb(241, 152, 152);
}

.submit:hover,
.close:hover {
  cursor: pointer;
}
</style>
