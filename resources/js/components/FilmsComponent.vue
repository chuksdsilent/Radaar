<template>
<div class="container mb-4">
    <div class=" justify-content-center">
        <div class="col-md-12">
            <div class="card">
                <div class="card-header">Films</div>

                <div class="card-body">
                    <table class="table">
                        <thead>
                            <th>Director</th>
                            <th>Producer</th>
                            <th>title</th>
                            <th>Opening Crawl</th>
                            <th>Created</th>
                        </thead>
                        <tbody>
                            <tr v-for="film in films" >
                                <td>{{film.director}}</td>
                                <td>{{film.producer}}</td>                                
                                <td>{{film.title}}</td>                                
                                <td>{{film.opening_crawl}}</td>
                                <td>{{film.created}}</td>
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
               films:[]
           }
        },
        created(){
            this.fetchFilm();
        },
        methods: {
            fetchFilm(){
                fetch('https://swapi.dev/api/films')
                .then(res => res.json())
                .then(res =>{
                    this.films = res.results;
                    console.log(res.results);
                })
            }
        }

    }
</script>
