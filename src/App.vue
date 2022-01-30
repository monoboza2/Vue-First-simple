<template>
  <header>
    <h1>ระบบจัดการข้อมูลพนักงาน</h1>
  </header>
  <FormComponent @save="insertemp"></FormComponent>
  <section class="employee-content" v-if="employees.length>0">
    <h1>ข้อมูลพนักงาน</h1>
    <ListData :employees="employees"/>
  </section>
</template>

<script>
import FormComponent from "./components/formcomponent.vue";
import ListData from "./components/Listdata.vue";
export default {
  name: "App",
  components: {
    ListData,
    FormComponent,
  },
  data(){
    return{
      employees:[]
    }
  },
 methods:{
    insertemp(data){
      this.employees.push(data)
    }
  }
};
</script>

<style scoped>
* {
  box-sizing: border-box;
}
body {
  margin: 0;
}
header {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 3rem;
  border-radius: 10px;
  padding: 1rem;
  background-color: purple;
  color: white;
  text-align: center;
}
.employee-content {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 3rem;
  border-radius: 10px;
  padding: 1rem;
  text-align: center;
}
.employee-content h1 {
  font-size: 2rem;
  border-bottom: 4px solid #ccc;
  color: purple;
  margin: 0 0 3rem 0;
  text-align: center;
}
</style>
