<template>
<div class="container mb-4">
    <div class=" justify-content-center">
        <div class="col-md-12">
            <div class="card">
                <div class="card-header">Planet</div>

                <div class="card-body">
                    <table class="table">
                        <thead>
                            <th>Climate</th>
                            <th>Diameter</th>
                            <th>Gravity</th>
                            <th>Name</th>
                            <th>edited</th>
                        </thead>
                        <tbody>
                            <tr v-for="planet in planets" >
                                <td>{{planet.climate}}</td>
                                <td>{{planet.diameter}}</td>                                
                                <td>{{planet.gravity}}</td>                                
                                <td>{{planet.name}}</td>
                                <td>{{planet.edited}}</td>
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
               planets:[]
           }
        },
        created(){
            this.fetchPlanet();
        },
        methods: {
            fetchPlanet(){
                fetch('https://swapi.dev/api/planets')
                .then(res => res.json())
                .then(res =>{
                    this.planets = res.results;
                })
            }
        }

    }
</script>
