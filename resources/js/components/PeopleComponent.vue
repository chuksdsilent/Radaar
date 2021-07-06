<template>
<div class="container">
    <div class=" justify-content-center">
        <div class="col-md-12">
            <div class="card">
                <div class="card-header">People</div>

                <div class="card-body">
                  
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
                    console.log(res);
                })
            }
        }

    }
</script>
