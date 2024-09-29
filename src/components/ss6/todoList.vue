<template>
  <div class="todo-container">
    <div class="input-container">
      <input
        type="text"
        v-model="newJobTitle"
        placeholder="Enter your job"
        class="job-input"
      />
      <button @click="addJob" class="add-btn">Add Job</button>
    </div>

    <div>
      <ul class="job-list">
        <li v-for="(job, index) in jobs" :key="index" class="job-item">
          <div class="job-details">
            <input
              type="checkbox"
              v-model="job.completed"
              class="job-checkbox"
            />
            <label :class="{ completed: job.completed }">{{ job.title }}</label>
          </div>
          <button @click="deleteJob(index)" class="delete-btn">Delete</button>
        </li>
      </ul>
    </div>

    <div class="completed-info">
      Số công việc hoàn thành: <strong>{{ completedJobs }}</strong> /
      {{ jobs.length }} công việc
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from "vue";

const jobs = ref([
  { title: "Code", completed: false },
  { title: "Homework", completed: false },
  { title: "Learn English", completed: true },
]);

const newJobTitle = ref("");

const addJob = () => {
  if (newJobTitle.value.trim() !== "") {
    const newJob = { title: newJobTitle.value, completed: false };
    jobs.value.push(newJob);
    newJobTitle.value = ""; 
  }
};

const deleteJob = (index) => {
  jobs.value.splice(index, 1);
};

const completedJobs = computed(
  () => jobs.value.filter((job) => job.completed).length
);
</script>

<style>
.todo-container {
  width: 700px;
  padding: 20px;
  border: 1px solid #ddd;
  border-radius: 8px;
  background-color: #f9f9f9;
}

.input-container {
  display: flex;
  justify-content: space-between;
  margin-bottom: 20px;
}

.job-input {
  width: 80%;
  padding: 8px;
  border: 1px solid #ccc;
  border-radius: 4px;
}

.add-btn {
  padding: 8px 12px;
  background-color: #007bff;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.add-btn:hover {
  background-color: #0056b3;
}

.job-list {
  list-style-type: none;
  padding: 0;
}

.job-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 10px;
}

.job-details {
  display: flex;
  align-items: center;
}

.job-checkbox {
  margin-right: 10px;
}

.completed {
  text-decoration: line-through;
  color: #999;
}

.delete-btn {
  padding: 5px 10px;
  background-color: #ff4d4d;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.delete-btn:hover {
  background-color: #ff1a1a;
}

.completed-info {
  padding: 10px;
  margin-top: 20px;
  background-color: #e0e0e0;
  border-radius: 4px;
  font-weight: bold;
  text-align: center;
}
</style>
