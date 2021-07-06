<template>
<div class="container mb-4">
    <div class=" justify-content-center">
        <div class="col-md-12">
            <div class="card">
                <div class="card-header">Starship</div>

                <div class="card-body">
                    <table class="table">
                        <thead>
                            <th>Cargo Capacity</th>
                            <th>Consumables</th>
                            <th>Crew</th>
                            <th>Name</th>
                            <th>Model</th>
                        </thead>
                        <tbody>
                            <tr v-for="starship in starships" >
                                <td>{{starship.cargo_capacity}}</td>
                                <td>{{starship.consumables}}</td>                                
                                <td>{{starship.crew}}</td>                                
                                <td>{{starship.name}}</td>
                                <td>{{starship.model}}</td>
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
               starships:[]
           }
        },
        created(){
            this.fetchStarships();
        },
        methods: {
            fetchStarships(){
                fetch('https://swapi.dev/api/starships')
                .then(res => res.json())
                .then(res =>{
                    this.starships = res.results;                    
                })
            }
        }

    }
</script>
