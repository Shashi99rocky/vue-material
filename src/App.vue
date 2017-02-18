<template>
  <div id="app">
    <md-card>
      <md-card-header>
        <div class="md-title"> Title</div>
        <div class="md-subhead">sub Title </div>
      </md-card-header>
      <md-card-content>
        <md-button class="md-raised md-primary" v-on:click.native="fillTable">Fill World</md-button>
        <md-button class="md-raised md-primary" v-on:click.native="clearTable">Clear World</md-button>

      </md-card-content>

      <md-table>
        <md-table-header>
          <md-table-row>
            <md-table-head>Name</md-table-head>
            <md-table-head>Age</md-table-head>
            <md-table-head>Email</md-table-head>
          </md-table-row>
        </md-table-header>
        <md-table-body>
          <md-table-row v-for="contact in contacts">
            <md-table-cell>{{contact.name}}</md-table-cell>
            <md-table-cell>{{contact.age}}</md-table-cell>
            <md-table-cell>{{contact.email}}</md-table-cell>
            
          </md-table-row>
        </md-table-body>
      </md-table>
    </md-card>
  </div>
</template>

<script>
    export default {
        name: 'app',
        data: function() {
            return {
                contacts: []
            }
        },
        methods: {
            fillTable: function() {

                this.contacts.push({
                    name: "jack",
                    age: 23,
                    email: "adc@gmail.com"
                });
                this.contacts.push({
                    name: "ammy",
                    age: 25,
                    email: "adc1@gmail.com"
                });
                this.contacts.push({
                    name: "Kemilly",
                    age: 26,
                    email: "ad2c@gmail.com"
                });
            },
            clearTable: function() {
                this.contacts.splice(0, this.contacts.length);
            }
        }
    }
</script>

<style>
    #app {
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
    }
</style>