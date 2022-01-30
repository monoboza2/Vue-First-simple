<template>
  <div>
    <ul>
      <Person
        v-for="(item,index) in employees"
        :key="index"
        :name="item.name"
        :salary="item.salary"
        :department="item.department"
        :gender="item.gender"
        :skill="item.language"
      />
      <!-- :id="item.id" -->
      <!-- @show="togglevisible"
       @delete="deletedata" -->
       <!-- :isvisible="item.isvisible" -->
    </ul>
  </div>
</template>

<script>
import Person from "./Person.vue";
export default {
  name: "ListData",
  components: {
    Person
  },
  props:["employees"]
//   data() {
//     return {
//       employees: [
//         {
//           id: 1,
//           name: "inca",
//           salary: 30000,
//           department: "Programer",
//           isvisible: false,
//         },
//         {
//           id: 2,
//           name: "inda",
//           salary: 25000,
//           department: "Marketing",
//           isvisible: false,
//         },
//         {
//           id: 3,
//           name: "indi",
//           salary: 15000,
//           department: "Marketing",
//           isvisible: false,
//         },
//         {
//           id: 4,
//           name: "ince",
//           salary: 20000,
//           department: "Programer",
//           isvisible: false,
//         },
//         {
//           id: 5,
//           name: "indo",
//           salary: 10000,
//           department: "B.A",
//           isvisible: false,
//         },
//         { id: 6, name: "inzo", department: "B.A", isvisible:false },
//       ],
//     };
//   },
//   methods: {
//     togglevisible(emp_id) {
//       this.employees=this.employees.map(item=>{
//         if(item.id===emp_id){
//           return{...item,isvisible:!item.isvisible}
//         }
//         return item
//       })
//     },
//     deletedata(emp_id){
//       this.employees=this.employees.filter(item=>{
//         return item.id!==emp_id
//       })
//     }
//   },
};
</script>

<style scoped>
ul {
  list-style: none;
  margin: 1rem 0;
  text-align: center;
}
</style>
