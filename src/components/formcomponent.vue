<template>
  <form @submit.prevent="submitform">
    <div class="formcontrol">
      <label for="emp-name">ชื่อพนักงาน:</label>
      <input
        type="text"
        name="emp-name"
        id="emp-name"
        v-model.trim="inputemployee.name"
      />
    </div>
    <div class="formcontrol">
      <label for="emp-salary">เงินเดือน:</label>
      <input
        type="number"
        name="emp-salary"
        id="emp-salary"
        v-model.trim="inputemployee.salary"
      />
    </div>
    <div class="formcontrol">
      <label for="emp-department">ตำแหน่งงาน:</label>
      <select v-model="inputemployee.department">
        <option value="ฝ่ายการตลาด">ฝ่ายการตลาด</option>
        <option value="ฝ่ายการเงิน">ฝ่ายการเงิน</option>
        <option value="ฝ่ายบริการ">ฝ่ายบริการ</option>
        <option value="โปรแกรมเมอร์">โปรแกรมเมอร์</option>
        <option value="โปรเจคเมเนเจอร์">โปรเจคเมเนเจอร์</option>
      </select>
    </div>

    <div class="formcontrol">
      <h2>เพศ:</h2>
      <div>
        <input
          type="radio"
          value="ชาย"
          id="male"
          v-model="inputemployee.gender"
        />
        <label for="emp-gender" id="male">ชาย</label>
      </div>
      <div>
        <input
          type="radio"
          value="หญิง"
          id="female"
          v-model="inputemployee.gender"
        />
        <label for="emp-gender" id="female">หญิง</label>
      </div>
    </div>
    <div class="formcontrol">
      <h2>ทักษะด้านภาษา:</h2>
      <div>
        <input
          type="checkbox"
          value="อังกฤษ"
          id="eng"
          v-model="inputemployee.language"
        />
        <label for="skill" id="eng">อังกฤษ</label>
      </div>
      <div>
        <input
          type="checkbox"
          value="ญี่ปุ่น"
          id="่jpy"
          v-model="inputemployee.language"
        />
        <label for="skill" id="jpy">ญี่ปุ่น</label>
      </div>
      <div>
        <input
          type="checkbox"
          value="จีน"
          id="่jpy"
          v-model="inputemployee.language"
        />
        <label for="skill" id="chn">จีน</label>
      </div>
    </div>

    <div>
      <button>บันทึกข้อมูล</button>
    </div>
    {{ JSON.stringify(inputemployee) }}
  </form>
</template>

<script>
export default {
  name: "FormComponent",
  data() {
    return {
      inputemployee: {
        name: "",
        salary: 0,
        department: "",
        gender: "",
        language:[],
      },
    };
  },
  methods:{
      submitform(){
        const newemp={
            name:this.inputemployee.name,
            salary:this.inputemployee.salary,
            department:this.inputemployee.department,
            gender:this.inputemployee.gender,
            language:this.inputemployee.language,
        }
        this.$emit("save",newemp);
        this.resetform();
      },
      resetform(){
          this.inputemployee.name="",
          this.inputemployee.salary=0
          this.inputemployee.department="",
          this.inputemployee.gender="",
          this.inputemployee.language=[]
      }
  }
};
</script>

<style scoped>
form {
  margin: 2rem auto;
  max-width: 40rem;
  border-radius: 12px;
  box-shadow: 2px 10px rgba(0, 0, 0, 0.25);
  padding: 2rem;
  background: #fff;
}
.formcontrol {
  margin: 0.5rem 0;
}
label {
  font-weight: bold;
}
input,
select {
  display: block;
  width: 100%;
  font: inherit;
  margin-top: 0.5rem;
}
button {
  font: inherit;
  font-weight: bold;
  background: pink;
  color: white;
  cursor: pointer;
  padding: 0.75rem 2rem;
  border-radius: 15px;
}
input[type="radio"],input[type="checkbox"]{
  display: inline-block;
  width: auto;
  margin-right: 3rem;
}
input[type="radio"] + label,input[type="checkbox"] + label {
  font-weight: normal;
}
h2 {
  font-size: 1rem;
  margin: 0.5rem 0;
}
</style>
