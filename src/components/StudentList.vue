<template>
  <div>
    <h1>Hello World - Student Lists</h1>
    <input type="text" v-model="name">
    <p>
      {{ name }}
    </p>
    <button @click.prevent="addToList"
    @keypress.enter="addToList"
    >Add to List</button>
    <ul>
      <li v-for="(student, index) in students">

        {{ student }}
        <button style="float:left;margin-right:10px"
        @click.prevent="removeItem(index)"
        >Delete</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'StudentList',
  data () {
    return {
      name:'',
      students: [
        "Student 1",
        "Student 2",
        "Student 3",
        "Student 4",
        "Student 5",
        "Student 6",
      ],
    }
  },
  methods: {
    addToList() {
      if (this.name.length) {
        this.students.push(this.name);
        this.name = "";
      } else {
        alert("Student Name Cannot be empty");
      }
    },

    removeItem(index) {
      this.students.splice(index,1);
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
