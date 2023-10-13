<template>
    <div>
        <nav class="nav">
            <router-link to="/" class="menu-bar">
                <span>Vue</span> Movie
            </router-link>
        </nav>
        <main>
            <router-view />
        </main>
    </div>
</template>

<style scoped>

    * {
        margin: 0;
        padding: 0;
    }

    .nav {
        background-color: rgb(72, 78, 78);
        padding: 15px 0;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .nav .menu-bar {
        color: white;
        text-decoration: none;
        font-size: 35px;
        font-weight: 700;
    }

    span {
        color: #42b883;
    }

</style>

