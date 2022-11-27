<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div class="offset-md-1 col-md-10 offset-md-1 border border-primary" style="padding: 10px">

    <form @submit.prevent="handleSubmit">
      <div class="form-group">
        <label for="companyName">Company Name</label>
        <input
          type="text"
          v-model="companyInfo.companyName"
          id="companyName"
          name="companyName"
          class="form-control"
          
        />
        
      </div>
      <div class="form-group">
        <label for="contact">Contact</label>
        <input
          type="text"
          v-model="companyInfo.contact"
          id="contact"
          name="contact"
          class="form-control"
          
        />
        
      </div>
      <div class="form-group">
        <label for="country">Country</label>
        <input
          type="country"
          v-model="companyInfo.country"
          id="country"
          name="country"
          class="form-control"
          
        />
        
      </div>
      
      <div class="form-group">
        <button class="btn btn-primary">Register</button>
      </div>
    </form>
    </div>
    <div class="offset-md-1 col-md-10 offset-md-1" style="padding: 10px">
      <table id="customers" class="table table-striped table-bordered">
        <thead>
          <tr>
            <th>Company</th>
            <th>Contact</th>
            <th>Country</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="company in companies" :key="company.id">
            <td>{{ company.companyName }}</td>
            <td>{{ company.contact }}</td>
            <td>{{ company.country }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data() {
    return {
      companyInfo: {
        companyName: "",
        contact: "",
        country: "",
      },
      submitted: false,
    };
  },
  methods: {
    handleSubmit() {
      this.submitted = true;
      this.companies.push(
      this.companyInfo
      )
      alert("SUCCESS!! :-)\n\n" + "Company created successful")
      
    },
  },
  setup() {
    // make companies variable reactive with the ref() function
    const companies = ref([
      {
        companyName: "Alfreds Futterkiste",
        contact: "Maria Anders",
        country: "Germany",
      },
      {
        companyName: "Berglunds snabbköp",
        contact: "Christina Berglund",
        country: "Sweden",
      },
      {
        companyName: "Centro comercial Moctezuma",
        contact: "Francisco Chang",
        country: "Mexico",
      },
      {
        companyName: "Ernst Handel",
        contact: "Roland Mendel",
        country: "Austria",
      },
      {
        companyName: "Island Trading",
        contact: "Helen Bennett",
        country: "UK",
      },
      {
        companyName: "Königlich Essen",
        contact: "Philip Cramer",
        country: "Canada",
      },
      {
        companyName: "Laughing Bacchus Winecellars",
        contact: "Yoshi Tannamuri",
        country: "Italy",
      },
    ]);

    return {
      companies,
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

#customers {
  font-family: Arial, Helvetica, sans-serif;
  border-collapse: collapse;
  width: 100%;
}

#customers td,
#customers th {
  border: 1px solid #ddd;
  padding: 8px;
}

#customers tr:nth-child(even) {
  background-color: #f2f2f2;
}

#customers tr:hover {
  background-color: #ddd;
}

#customers th {
  padding-top: 12px;
  padding-bottom: 12px;
  text-align: left;
  background-color: #04aa6d;
  color: white;
}
</style>
