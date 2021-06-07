<template>
  <section>
    <h1>Data Table</h1>
    <v-data-table
      :headers="headers"
      :items="employees"
      :items-per-page="5"
      class="elevation-1"
      @click:row="selectRow"
      multi-sort
    ></v-data-table>

    <v-snackbar v-model="snackbar">
      You have selected {{ currentItem.name }}, {{ currentItem.title }}

      <template v-slot:action="{ attrs }">
        <v-btn color="pink" text v-bind="attrs" @click="snackbar = false">
          Close
        </v-btn>
      </template>
    </v-snackbar>
  </section>
</template>

<script>
import employeeData from '../data/employees.json';
export default {
  data() {
    return {
      snackbar: false,
      currentItem: {
        name: '',
        title: '',
      },
      headers: [
        {
          text: 'ID',
          align: 'start',
          sortable: true,
          value: 'id',
        },
        { text: 'Name', value: 'name' },
        { text: 'Title', value: 'title' },
        { text: 'Salary', value: 'salary' },
      ],

      employees: employeeData,
    };
  },
  methods: {
    selectRow(event) {
      this.snackbar = true;
      this.currentItem.name = event.name;
      this.currentItem.title = event.title;
    },
  },
};
</script>

<style></style>
