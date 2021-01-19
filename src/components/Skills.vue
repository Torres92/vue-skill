<template>
  <div class="hello">
    <div class="holder">
      <form @submit.prevent="addSkill">
        <!-- <Form v-slot="{ errors }">
          <Field name="field" :rules="isRequired" />

          <span>{{ errors.field }}</span> -->
          <input type="text" placeholder="Enter a skill" v-model="skill" />
        <!-- </Form> -->
        <!-- <input type="checkbox" v-model="checked" id="checkbox"> -->
      </form>
      <ul>
        <li v-for="(data, index) in skills" :key="index">
          {{ index }}. {{ data.skill }}
        </li>
      </ul>

      <!-- <div v-bind:class="{ alert: showAlert, 'another-class': showClass }"></div>
       </div> -->

      <!-- <div v-bind:class="alertObject"></div>
       </div> -->

      <p>These are the skills that you possess.</p>
      <!-- 
       <div v-bind:style="{ backgroundColor: bgColor, width: bgWidth, height: bgHeight }"></div>
       </div> -->
    </div>
  </div>
</template>

<script>
// import { Field, Form } from "vee-validate";

export default {
  name: "Skills",
  // components: {
  //   Field,
  //   Form,
  // },
  data() {
    return {
      // checked: false,

      skill: "",
      skills: [{ skill: "Vue.js" }, { skill: "Frontend Developer" }],
      // showAlert: true,
      // showClass: true,
      // alertObject: {
      //   alert: true
      // }

      // bgColor: "yellow",
      // bgWidth: "100%",
      // bgHeight: "30px",
    };
  },
  methods: {
     // Validator function
    isRequired(value) {
      return value ? true : 'This field is required';
    },
    addSkill() {
      this.skills.push({ skill: this.skill }), (this.skill = "");
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.holder {
  background: #ffffff;
}

ul {
  margin: 0;
  padding: 0;
  list-style-type: none;
}

ul li {
  padding: 20px;
  font-size: 1.3em;
  background-color: #e0edf4;
  border-left: 5px solid #3eb3f6;
  margin-bottom: 2px;
  color: #3e5252;
}

p {
  text-align: center;
  padding: 30px 0;
  color: gray;
}

.container {
  box-shadow: 0px 0px 40px lightgray;
}

input {
  width: calc(100% - 40px);
  border: 0;
  padding: 20px;
  font-size: 1.3em;
  background-color: #323333;
  color: #687f7f;
}
</style>
