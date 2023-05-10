<template>
  <main class="app">
		
		<section class="greeting">
			<h1 class="title"><b>
				Welcome To Rahmayani's To Do List </b>
			</h1><hr><hr>
		</section>
    <section class="create-todo">
			<h3><b>Tambahkan kegiatan yang akan dilakukan!</b></h3>
  <form id="new-todo-form" @submit.prevent="addTodo">
    <input type="text" 
					name="content" 
					id="content" 
					placeholder="Cth : Memasak" v-model="newTodo">
    <button class="tugas">Tambahkan Kegiatan</button>
  </form>
  </section>
  <section class="todo-list">
			<h3><b>LIST KEGIATAN:</b></h3>
      <div v-for="todo in filteredTodos" :class="`todo-item ${todo.done && 'done'}`">
					<label>
            <ul>
						<input type="checkbox" class="styled-checkbox" v-model="todo.done" >
						<span :class="{ done: todo.done }">{{ todo.text }}</span>
						
			
            </ul>
					</label>

					<div class="todo-content">
						<input type="text" v-model="todo.content" />
					</div>
					
					<div class="actions">
						<button class="delete" @click="removeTodo(todo)">Hapus</button>
					</div>
				</div>
				<div>
				<button class="hide" @click="hideCompleted = !hideCompleted">
   				 {{ hideCompleted ? 'Tampilkan Semua' : 'Sembunyikan yang Selesai' }}
  	</button></div>

		</section>
		
	</main>
	
</template>

<script>
import { ref, computed } from 'vue'

let id = 0

const newTodo = ref('')
const hideCompleted = ref(false)
const todos = ref([
  { id: id++, text: 'Sholat Tahajud dan Subuh', done: true },
  { id: id++, text: 'Memmasak dan menyapu kamar', done: true },
  { id: id++, text: 'Mandi dan bersiap ke kampus', done: false }
])

const filteredTodos = computed(() => {
  return hideCompleted.value
    ? todos.value.filter((t) => !t.done)
    : todos.value
})

function addTodo() {
  todos.value.push({ id: id++, text: newTodo.value, done: false })
  newTodo.value = ''
}

function removeTodo(todo) {
  todos.value = todos.value.filter((t) => t !== todo)
}
</script>

<style>
.done {
  text-decoration: line-through;
}
</style>