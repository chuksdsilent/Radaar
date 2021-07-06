<template>
<div class="container mb-4">
    <div class=" justify-content-center">
        <div class="col-md-12">
            <div class="card">
                <div class="card-header">People</div>

                <div class="card-body">
                    <table class="table">
                        <thead>
                            <th>Name</th>
                            <th>Birth Year</th>
                            <th>Hair Color</th>
                            <th>Skin Color</th>
                            <th>Mass</th>
                        </thead>
                        <tbody>
                            <tr v-for="person in people">
                                <td>{{person.name}}</td>
                                <td>{{person.birth_year}}</td>
                                <td>{{person.hair_color}}</td>
                                <td>{{person.skin_color}}</td>
                                <td>{{person.mass}}</td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
        </div>
    </div>
</div>
</template>

<script>
    export default {
         data(){
           return{
               people:[]
           }
        },
        created(){
            this.fetchPeople();
        },
        methods: {
            fetchPeople(){
                fetch('https://swapi.dev/api/people')
                .then(res => res.json())
                .then(res =>{
                    this.people = res.results;
                    
                })
            }
        }

    }
</script>
