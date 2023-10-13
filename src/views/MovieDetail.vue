<template>
    <div class="container mt-2">
        <div class="card py-4 px-3 movie-detail">
            <div class="left">
                <div class="poster">
                    <img :src="movie.Poster" />
                    <div class="middle">
                        <div class="text">
                            <svg class="svg" xmlns="http://www.w3.org/2000/svg" height="4rem" viewBox="0 0 512 512"><path d="M0 256a256 256 0 1 1 512 0A256 256 0 1 1 0 256zM188.3 147.1c-7.6 4.2-12.3 12.3-12.3 20.9V344c0 8.7 4.7 16.7 12.3 20.9s16.8 4.1 24.3-.5l144-88c7.1-4.4 11.5-12.1 11.5-20.5s-4.4-16.1-11.5-20.5l-144-88c-7.4-4.5-16.7-4.7-24.3-.5z"/>
                            </svg>
                        </div>
                    </div>   
                </div>
                <div class="d-flex flex-row justify-content-between mt-4">
                    <div>
                        <div class=" card px-3 py-1 card p-0 d-flex flex-row justify-content-center align-items-center text-center " style=" cursor: pointer;">
                            <svg xmlns="http://www.w3.org/2000/svg" height="18px" viewBox="0 0 512 512"><path d="M323.8 34.8c-38.2-10.9-78.1 11.2-89 49.4l-5.7 20c-3.7 13-10.4 25-19.5 35l-51.3 56.4c-8.9 9.8-8.2 25 1.6 33.9s25 8.2 33.9-1.6l51.3-56.4c14.1-15.5 24.4-34 30.1-54.1l5.7-20c3.6-12.7 16.9-20.1 29.7-16.5s20.1 16.9 16.5 29.7l-5.7 20c-5.7 19.9-14.7 38.7-26.6 55.5c-5.2 7.3-5.8 16.9-1.7 24.9s12.3 13 21.3 13L448 224c8.8 0 16 7.2 16 16c0 6.8-4.3 12.7-10.4 15c-7.4 2.8-13 9-14.9 16.7s.1 15.8 5.3 21.7c2.5 2.8 4 6.5 4 10.6c0 7.8-5.6 14.3-13 15.7c-8.2 1.6-15.1 7.3-18 15.1s-1.6 16.7 3.6 23.3c2.1 2.7 3.4 6.1 3.4 9.9c0 6.7-4.2 12.6-10.2 14.9c-11.5 4.5-17.7 16.9-14.4 28.8c.4 1.3 .6 2.8 .6 4.3c0 8.8-7.2 16-16 16H286.5c-12.6 0-25-3.7-35.5-10.7l-61.7-41.1c-11-7.4-25.9-4.4-33.3 6.7s-4.4 25.9 6.7 33.3l61.7 41.1c18.4 12.3 40 18.8 62.1 18.8H384c34.7 0 62.9-27.6 64-62c14.6-11.7 24-29.7 24-50c0-4.5-.5-8.8-1.3-13c15.4-11.7 25.3-30.2 25.3-51c0-6.5-1-12.8-2.8-18.7C504.8 273.7 512 257.7 512 240c0-35.3-28.6-64-64-64l-92.3 0c4.7-10.4 8.7-21.2 11.8-32.2l5.7-20c10.9-38.2-11.2-78.1-49.4-89zM32 192c-17.7 0-32 14.3-32 32V448c0 17.7 14.3 32 32 32H96c17.7 0 32-14.3 32-32V224c0-17.7-14.3-32-32-32H32z"/>
                            </svg>
                            &nbsp;&nbsp;Like
                        </div> 
                    </div>

                    <div>
                       <div class=" card px-3 py-1 card p-0 d-flex flex-row justify-content-center align-items-center text-center " style=" cursor: pointer;">
                            <svg xmlns="http://www.w3.org/2000/svg" height="18px" viewBox="0 0 512 512"><path d="M323.8 477.2c-38.2 10.9-78.1-11.2-89-49.4l-5.7-20c-3.7-13-10.4-25-19.5-35l-51.3-56.4c-8.9-9.8-8.2-25 1.6-33.9s25-8.2 33.9 1.6l51.3 56.4c14.1 15.5 24.4 34 30.1 54.1l5.7 20c3.6 12.7 16.9 20.1 29.7 16.5s20.1-16.9 16.5-29.7l-5.7-20c-5.7-19.9-14.7-38.7-26.6-55.5c-5.2-7.3-5.8-16.9-1.7-24.9s12.3-13 21.3-13L448 288c8.8 0 16-7.2 16-16c0-6.8-4.3-12.7-10.4-15c-7.4-2.8-13-9-14.9-16.7s.1-15.8 5.3-21.7c2.5-2.8 4-6.5 4-10.6c0-7.8-5.6-14.3-13-15.7c-8.2-1.6-15.1-7.3-18-15.2s-1.6-16.7 3.6-23.3c2.1-2.7 3.4-6.1 3.4-9.9c0-6.7-4.2-12.6-10.2-14.9c-11.5-4.5-17.7-16.9-14.4-28.8c.4-1.3 .6-2.8 .6-4.3c0-8.8-7.2-16-16-16H286.5c-12.6 0-25 3.7-35.5 10.7l-61.7 41.1c-11 7.4-25.9 4.4-33.3-6.7s-4.4-25.9 6.7-33.3l61.7-41.1c18.4-12.3 40-18.8 62.1-18.8H384c34.7 0 62.9 27.6 64 62c14.6 11.7 24 29.7 24 50c0 4.5-.5 8.8-1.3 13c15.4 11.7 25.3 30.2 25.3 51c0 6.5-1 12.8-2.8 18.7C504.8 238.3 512 254.3 512 272c0 35.3-28.6 64-64 64l-92.3 0c4.7 10.4 8.7 21.2 11.8 32.2l5.7 20c10.9 38.2-11.2 78.1-49.4 89zM32 384c-17.7 0-32-14.3-32-32V128c0-17.7 14.3-32 32-32H96c17.7 0 32 14.3 32 32V352c0 17.7-14.3 32-32 32H32z"/>
                            </svg>
                            &nbsp;&nbsp;Dislike
                        </div> 
                    </div>
                </div>
            </div>
            <div class="right px-5">
                <div class="d-flex flex-row justify-content-between">
                    <div>
                        <div class=" card px-3 py-2 card p-0 d-flex flex-row justify-content-center align-items-center text-center " style=" cursor: pointer;">
                            <svg xmlns="http://www.w3.org/2000/svg" height="1em" viewBox="0 0 384 512"><path d="M73 39c-14.8-9.1-33.4-9.4-48.5-.9S0 62.6 0 80V432c0 17.4 9.4 33.4 24.5 41.9s33.7 8.1 48.5-.9L361 297c14.3-8.7 23-24.2 23-41s-8.7-32.2-23-41L73 39z"/>
                            </svg>
                            &nbsp;&nbsp;Watch now
                        </div> 
                    </div>

                    <div>
                       <div class=" card px-3 py-2 card p-0 d-flex flex-row justify-content-center align-items-center text-center " style=" cursor: pointer;">
                            <svg xmlns="http://www.w3.org/2000/svg" height="1em" viewBox="0 0 448 512"><path d="M256 80c0-17.7-14.3-32-32-32s-32 14.3-32 32V224H48c-17.7 0-32 14.3-32 32s14.3 32 32 32H192V432c0 17.7 14.3 32 32 32s32-14.3 32-32V288H400c17.7 0 32-14.3 32-32s-14.3-32-32-32H256V80z"/></svg>
                            &nbsp;&nbsp;Add to favorite
                        </div> 
                    </div>
                </div>
                <div>
                    <div class="my-4">
                        <p style="font-size: 35px; font-weight: 600">
                            {{ movie.Title }}
                        </p>
                        <p class="card p-2 d-inline" style="margin-right: 7px;  cursor: pointer; ">
                            <svg xmlns="http://www.w3.org/2000/svg" height="1em" viewBox="0 0 576 512"><path d="M0 128C0 92.7 28.7 64 64 64H320c35.3 0 64 28.7 64 64V384c0 35.3-28.7 64-64 64H64c-35.3 0-64-28.7-64-64V128zM559.1 99.8c10.4 5.6 16.9 16.4 16.9 28.2V384c0 11.8-6.5 22.6-16.9 28.2s-23 5-32.9-1.6l-96-64L416 337.1V320 192 174.9l14.2-9.5 96-64c9.8-6.5 22.4-7.2 32.9-1.6z"/></svg>
                            Trailer
                        </p>
                        <p class="card p-2 d-inline"><span>HD</span></p>
                    </div>
                    <div>
                        <p>{{ movie.Plot }}</p>
                    </div>
                    <div class="d-flex flex-row justify-content-between">
                        <div>
                            <p><span>Genre</span> : {{ movie.Genre }}</p>
                            <p><span>Country</span> : {{ movie.Country }}</p>
                            <p><span>Director</span> : {{ movie.Director }}</p>
                        </div>
                        <div>
                            <p><span>Cast</span> : {{ movie.Actors }}</p>
                            <p><span>Language</span> : {{ movie.Language }}</p>
                            <p><span>Released</span> : {{ movie.Released }}</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import { ref, onBeforeMount } from "vue";
import { useRoute } from "vue-router";
import env from "../env";
export default {
    setup() {
        const movie = ref({});
        const route = useRoute();

        onBeforeMount(() => {
            fetch(
                `https://www.omdbapi.com/?apikey=${env.apiKey}&i=${route.params.id}&plot=full`
            )
                .then((res) => res.json())
                .then((data) => {
                    movie.value = data;
                });
        });

        return {
            movie,
        };
    },
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=AR+One+Sans&family=Fira+Sans&display=swap");
    * {
        font-family: "Fira Sans", sans-serif;
    }

    .poster {
        position: relative;
        z-index: 2;
        transition: all 900ms;
        background-color: black;
    }

    .middle {
        transition: .5s ease;
        opacity: 0;
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        -ms-transform: translate(-50%, -50%);
        text-align: center;
        z-index: 0;
    }

    .poster:hover .middle {
    opacity: 1;
    transition: all 700ms;
    
    }

    .poster:hover img {
    opacity: 0.4;
    transition: all 700ms;
    cursor: pointer;
    }

    .text {
    color: white;
    cursor: pointer;
    }

    .svg {
        fill: white;
    }

    .card-subtitle {
        font-size: 16px;
        font-weight: 600;
        white-space: nowrap;
        overflow: hidden;
        text-overflow: ellipsis;
        max-width: 100%;
    }
    .movie-detail {
        display: flex;
        flex-direction: row;
    }
    span {
        font-weight: 600;
    }
</style>