<script setup>
import { ref, onUpdated } from "vue";
const showModal = ref(false);
const newNote = ref("");
const notes = ref([]);
const errMsg = ref("");

const addNote = () => {
  if (newNote.value.length < 5) return (errMsg.value = "Write some more ...");
  notes.value.push({
    id: Math.floor(Math.random() * 100000),
    text: newNote.value,
    date: new Date().toLocaleDateString("en-US"),
    backgroundColor: getRandomColor(),
  });
  showModal.value = false;
  newNote.value = "";
};

function getRandomColor() {
  return "hsl(" + Math.random() * 360 + ", 100%, 75%)";
}

onUpdated(() => {
  if (newNote.value.length >= 5) {
    console.log("New Note is more than five");
    errMsg.value = "";
  }
});
</script>

<template>
  <main class="notes-page">
    <div class="notes-heading">
      <h1>Notes</h1>
      <button @click="showModal = true" class="add-note">Add</button>
    </div>
    <div v-if="showModal" class="overlay">
      <div class="note-input-area">
        <div v-if="errMsg" class="errMsg">{{ errMsg }}</div>
        <textarea
          v-model="newNote"
          name="note-input"
          id=""
          cols="30"
          rows="10"
        ></textarea>
        <button class="submit" @click="addNote">Add Note</button>
        <button class="close" @click="showModal = false">Close</button>
      </div>
    </div>
    <div class="notes-container">
      <div
        v-for="note in notes"
        class="notes"
        :key="note.id"
        :style="{ backgroundColor: note.backgroundColor }"
      >
        <h4>
          {{ note.text }}
        </h4>
        <p>{{ note.date }}</p>
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
  width: 175px;
  height: 175px;
  padding: 10px 20px;
  border-radius: 15px;

  display: flex;
  flex-direction: column;
  justify-content: space-between;

  overflow-wrap: break-word;
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
  height: 400px;

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

.errMsg {
  color: rgb(224, 115, 115);
  margin: 10px 0;
}
</style>
