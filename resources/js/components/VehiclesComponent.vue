<template>
<div class="container mb-4">
    <div class=" justify-content-center">
        <div class="col-md-12">
            <div class="card">
                <div class="card-header">Vehicles</div>

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
                            <tr v-for="vehicle in vehicles" >
                                <td>{{vehicle.cargo_capacity}}</td>
                                <td>{{vehicle.consumables}}</td>                                
                                <td>{{vehicle.crew}}</td>                                
                                <td>{{vehicle.name}}</td>
                                <td>{{vehicle.model}}</td>
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
               vehicles:[]
           }
        },
        created(){
            this.fetchVehicles();
        },
        methods: {
            fetchVehicles(){
                fetch('https://swapi.dev/api/starships')
                .then(res => res.json())
                .then(res =>{
                    this.vehicles = res.results;
                
                })
            }
        }

    }
</script>
