<script>
export default {
  data() {
    return {
      firstname: "",
      lastname: "",
      email: "",
      prefix: null,
      phoneNumber: null,
      password: "",
    }
  },
  methods: {
    printObject() {
      console.log(JSON.stringify(this));
    }
  }
}
</script>

<template>

  <head>
    <title> Simple Form :) </title>
  </head>
  <main>

    <div class="simpleFormDiv">
      <form @submit="printObject">
        <div>
          <h4> Gini Apps - user form </h4>
        </div>
        <div class="formElement">
          <label> First name </label>
          <input v-model="firstname" placeholder="Enter your first name: " pattern="[a-zA-Z]{2,12}" required />
        </div>

        <div class="formElement">
          <label> Last name </label>
          <input v-model="lastname" placeholder="Enter your last name: " pattern="[a-zA-Z]{2,15}" required />
        </div>

        <div class="formElement">
          <label> Email address </label>
          <input v-model="email" placeholder="Enter your email address:  "
            pattern="[a-z0-9._%+-]+@[a-z0-9.-]+\.[a-z]{2,4}" required />
        </div>

        <div class="formElement">
          <label> Phone number </label>
          <div class="phoneElement">
            <select v-model="prefix" style="margin-right:10px; width: 50px;" required>
              <option disabled value=""> Please select the prefix</option>
              <option>050</option>
              <option>052</option>
              <option>054</option>
            </select>
            <input v-model="phoneNumber" placeholder="" pattern="\d{7}" required />
          </div>
        </div>

        <div class="formElement">
          <label> Password </label>
          <input type="password" v-model="password" placeholder="Enter your password: "
            pattern="(?=.*\d)(?=.*[a-z])(?=.*[a-zA-Z]).{8,}" required />
        </div>

        <div class="formElement">
          <input type="submit" value="Submit" />
        </div>

      </form>
    </div>
  </main>
</template>

<style>
.simpleFormDiv {
  background-color: lightgrey;
  width: 225px;
  padding: 10px;
  border-radius: 15px;
  font-family: Arial, Helvetica, sans-serif;
}

.formElement {
  display: flex;
  flex-direction: column;
  width: 200px;
  margin: 10px;
}

.phoneElement {
  display: flex;
}
</style>