<template>
    <div class="container">    
        <form class="serch-box my-4 text-center" @click.prevent="SearchMovie">
            <input type="text" class="form-control form-control-lg w-50 m-auto" placeholder=" Search movies... " v-model="search" style="font-size: 18px">
            <button class="btn btn-success mt-4 px-5 py-2">Search</button>
        </form>

        <div class="container mt-4">
            <div class="row" v-if="search == 0">
                <div class="col-auto mb-3">
                    <router-link to="/movie/tt6472976" style="text-decoration: none;">
                        <div class="card m-card" style="width: 18rem;">
                            <div class="card-body">
                                <div class="card-img">
                                    <img src="https://m.media-amazon.com/images/M/MV5BNzVmMjJlN2MtNWQ4Ny00Zjc2LWJjYTgtYjJiNGM5MTM1ZTlkXkEyXkFqcGdeQXVyMjM4NTM5NDY@._V1_SX300.jpg"  style="width: 250px; height:350px" class="rounded-1" >
                                </div>
                                <h6 class="card-subtitle mb-2 pt-4 pb-2 text-center">Five Feet Apart</h6>
                                <div class=" detail d-flex flex-row justify-content-between">
                                    <p>2019</p>
                                    <p class="border border-1 px-2 rounded-3 d-flex align-item-center justify-content-center" style="padding: 2px 0">Movie</p>
                                </div>
                            </div>
                        </div>
                    </router-link>
                </div>
                <div class="col-auto mb-3">
                    <router-link to="/movie/tt4799066" style="text-decoration: none;">
                        <div class="card m-card" style="width: 18rem;">
                            <div class="card-body">
                                <div class="card-img">
                                    <img src="https://m.media-amazon.com/images/M/MV5BMjg0NjU1MjgyNF5BMl5BanBnXkFtZTgwNzc5NjYyNDM@._V1_SX300.jpg" style="width: 250px; height:350px" class="rounded-1" >
                                </div>
                                <h6 class="card-subtitle mb-2 pt-4 pb-2 text-center">Midnight Sun</h6>
                                <div class=" detail d-flex flex-row justify-content-between">
                                    <p>2018</p>
                                    <p class="border border-1 px-2 rounded-3 d-flex align-item-center justify-content-center" style="padding: 2px 0">Movie</p>
                                </div>
                            </div>
                        </div>
                    </router-link>
                </div>
                <div class="col-auto mb-3">
                    <router-link to="/movie/tt8718158" style="text-decoration: none;">
                        <div class="card m-card" style="width: 18rem;">
                            <div class="card-body">
                                <div class="card-img">
                                    <img src="https://m.media-amazon.com/images/M/MV5BNDI2MDQzZDAtZmVlZS00MWU1LThkNzUtNjZmZmY3ZDljYjk2XkEyXkFqcGdeQXVyMTY5Nzc4MDY@._V1_SX300.jpg" style="width: 250px; height:350px" class="rounded-1" >
                                </div>
                                <h6 class="card-subtitle mb-2 pt-4 pb-2 text-center">The Hating Game</h6>
                                <div class=" detail d-flex flex-row justify-content-between">
                                    <p>2021</p>
                                    <p class="border border-1 px-2 rounded-3 d-flex align-item-center justify-content-center" style="padding: 2px 0">Movie</p>
                                </div>
                            </div>
                        </div>
                    </router-link>
                </div>
                <div class="col-auto mb-3">
                    <router-link to="/movie/tt15326988" style="text-decoration: none;">
                        <div class="card m-card" style="width: 18rem;">
                            <div class="card-body">
                                <div class="card-img">
                                    <img src="https://m.media-amazon.com/images/M/MV5BNGMzYWZlYmYtNTcyMC00ZGVjLThjN2ItMjY4MjkwN2NlMjYwXkEyXkFqcGdeQXVyOTU0NjY1MDM@._V1_SX300.jpg" style="width: 250px; height:350px" class="rounded-1" >
                                </div>
                                <h6 class="card-subtitle mb-2 pt-4 pb-2 text-center">Ghosted</h6>
                                <div class=" detail d-flex flex-row justify-content-between">
                                    <p>2023</p>
                                    <p class="border border-1 px-2 rounded-3 d-flex align-item-center justify-content-center" style="padding: 2px 0">Movie</p>
                                </div>
                            </div>
                        </div>
                    </router-link>
                </div>
            </div>


            <div class="row" v-else>
                <div class="col-auto mb-3"  v-for="movie in movies" :key="movie.imdbID">
                    <router-link :to="'/movie/' + movie.imdbID" style="text-decoration: none;">
                        <div class="card m-card" style="width: 18rem;">
                            <div class="card-body">
                                <div class="card-img">
                                    <img :src="movie.Poster" style="width: 250px; height:345px" class="rounded-1" >
                                </div>
                                <h6 class="card-subtitle mb-2 pt-4 pb-2 text-center">{{movie.Title}}</h6>
                                <div class=" detail d-flex flex-row justify-content-between">
                                    <p>{{movie.Year}}</p>
                                    <p class="border border-1 px-2 rounded-3 d-flex align-item-center justify-content-center" style="padding: 2px 0">{{movie.Type}}</p>
                                </div>
                            </div>
                        </div>
                    </router-link>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import env from '../env'

export default {
        data (){
            return {
                search: '',
                movies: [],
            }
        }, 
        
        methods: {
            SearchMovie () {
                if( this.search != ""){
                    fetch(`https://www.omdbapi.com/?apikey=${env.apiKey}&s=${this.search}`)
                    .then(res => res.json())
                    .then(data => {
                        this.movies = data.Search
                    })
                }
            }
        },
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=AR+One+Sans&family=Fira+Sans&display=swap');
    * {
        font-family: 'Fira Sans', sans-serif;
    }

    .card-subtitle  {
        font-size: 17px;
        font-weight: 600;
        white-space: nowrap;
        overflow: hidden;
        text-overflow: ellipsis;
        max-width: 100%;
    }

    .card-body {
        overflow: hidden;
    }

    .card-body .card-img{
        overflow: hidden;
    }

    .m-card .card-body .card-img img:hover{
        transform: scale(1.03);
        transition: all 700ms;
    }
</style>