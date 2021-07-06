<template>
<div class="container mb-4">
    <div class=" justify-content-center">
        <div class="col-md-12">
            <div class="card">
                <div class="card-header">Species</div>

                <div class="card-body">
                    <table class="table">
                        <thead>
                            <th>Average Height</th>
                            <th>Designation</th>
                            <th>Hair Colors</th>
                            <th>Name</th>
                            <th>Home World</th>
                        </thead>
                        <tbody>
                            <tr v-for="specie in species" >
                                <td>{{specie.average_height}}</td>
                                <td>{{specie.designation}}</td>                                
                                <td>{{specie.hair_colors}}</td>                                
                                <td>{{specie.name}}</td>
                                <td>{{specie.homeworld}}</td>
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
               species:[]
           }
        },
        created(){
            this.fetchVehicles();
        },
        methods: {
            fetchVehicles(){
                fetch('https://swapi.dev/api/species')
                .then(res => res.json())
                .then(res =>{
                    this.species = res.results;
                    console.log(res.results);
                })
            }
        }

    }
</script>
