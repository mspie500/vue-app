<template>
  <div
    id="app"
    
  >
  <employee-header />
  <div class="container"><about /></div>
  <div class="container border pb-5 mt-5 rounded shadow">
      <h2 class="text-center mt-2 border-bottom">Employee App</h2>
  
      <div class="row">
        
        <div class="col-md-6 my-auto">
          <h3 class="my-3 text-center border-bottom">Add Employee</h3>
          <employee-form @add:employee="addEmployee" />
          </div>
  
        <div class="col-md-6 my-auto">
           <div class="my-4 py-4 text-center">
            <img class="img-fluid mx-auto" src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/95/Vue.js_Logo_2.svg/512px-Vue.js_Logo_2.svg.png" alt="Card image cap">
            <div class="card-body">
               <p class="card-text">Built with Vue.js</p>
               <a href="https://vuejs.org/" title="vuejs homepage" class="btn btn-primary shadow">Learn More</a>
            </div>
         </div>
        </div>
      </div>
      <h3 class="text-center my-5 border-bottom">Employee Table</h3>
      <employee-table
        :employees="employees"
        @delete:employee="deleteEmployee"
        @edit:employee="editEmployee"
      />
  </div>
  <employee-footer />
  </div>
</template>

<script>
import EmployeeTable from '@/components/EmployeeTable.vue'
import EmployeeForm from '@/components/EmployeeForm.vue'
import EmployeeHeader from '@/components/EmployeeHeader.vue'
import EmployeeFooter from '@/components/EmployeeFooter.vue'
import About from '@/components/About.vue'

export default {
  name: "app",
  components: {
    EmployeeTable,
    EmployeeForm,
    EmployeeHeader,
    EmployeeFooter,
    About,
  },
  data() {
    return {
      employees: []
    }
  },

  mounted() {
    this.getEmployees()
  },

  methods: {
    async getEmployees() {
      try {
        const response = await fetch('https://jsonplaceholder.typicode.com/users')
        const data = await response.json()
        this.employees = data
      } catch (error) {
        /* console.error(error) */
      }
    },

    async addEmployee(employee) {
      try {
        const response = await fetch('https://jsonplaceholder.typicode.com/users', {
          method: 'POST',
          body: JSON.stringify(employee),
          headers: { "Content-type": "application/json; charset=UTF-8" }
        })
        const data = await response.json()
        this.employees = [...this.employees, data]
      } catch (error) {
        /* console.error(error) */
      }
    },

    async editEmployee(id, updatedEmployee) {
      try {
        const response = await fetch(`https://jsonplaceholder.typicode.com/users/${id}`, {
          method: 'PUT',
          body: JSON.stringify(updatedEmployee),
          headers: { "Content-type": "application/json; charset=UTF-8" }
        })
        const data = await response.json()
        this.employees = this.employees.map(employee => employee.id === id ? data : employee)
      } catch (error) {
        /* console.error(error) */
      }
    },

    async deleteEmployee(id) {
      try {
        await fetch(`https://jsonplaceholder.typicode.com/users/${id}`, {
          method: 'DELETE'
        })
        this.employees = this.employees.filter(employee => employee.id !== id)
      } catch (error) {
        /* console.error(error) */
      }
    },
  },
}
</script>

<style>
body {
  background-image: url('assets/paper.png');
}
/* button {
  background: #009435;
  border: 1px solid #009435;
}

button:hover,
button:active,
button:focus {
  background: #32a95d;
  border: 1px solid #32a95d;
}

.small-container {
  max-width: 680px;
} */
img {
  max-width: 150px !important;
}
</style>
