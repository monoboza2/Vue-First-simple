<template>
  <Card>
    <template v-slot:card-header>
      <h1>{{ name }}</h1>
    </template>
    <!-- <template v-slot:card-button>
      <button @click="showDescription(id)">ดูรายละเอียด</button>&nbsp;
      <button @click="deletedata(id)">ลบข้อมูล</button>
    </template> -->
    <template v-slot:card-content>
      <!-- <translation name="fade">
        <div v-show="isvisible"> -->
          <p>เพศ :{{gender}}</p>
          <p>ทักษะด้านภาษา :{{skill}}</p>
          <p>เงินเดือน :{{ salary }} บาท , ตำแหน่งงาน :{{ department }}</p>
        <!-- </div>
      </translation> -->
    </template>
  </Card>
</template>

<script>
import Card from "./Card.vue";
export default {
  components: { Card },
  name: "Person",
  props: {
    // id: {
    //   type: Number,
    //   required: true,
    // },
    name: {
      type: String,
      required: true,
    },
    salary: {
      type: Number,
      default: 0,
    },
    department: {
      type: String,
    },
    gender: {
      type:String,
    },
    skill:{
      type:Array,
    }
    // isvisible: {
    //   type: Boolean,
    //   default: false,
    // },
  },
  methods: {
    // showDescription(id) {
    //   this.$emit("show", id);
    // },
    // deletedata(id) {
    //   this.$emit("delete", id);
    // },
  },
};
</script>

<style scoped>
li {
  margin: 1rem 0;
  font-size: 1.25rem;
  font-weight: bold;
  background: #8ddba4;
  padding: 0.5rem;
  color: #1f1f1f;
  border-radius: 25px;
}
button {
  font: inherit;
  cursor: pointer;
  border: 1px solid #ff0077;
  background-color: #ff0077;
  color: white;
  padding: 0.5rem 1rem;
  box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.26);
}
.fade-enter-from {
  opacity: 0;
}
.fade-enter-active {
  transition: all 0.5s linear;
}
</style>
