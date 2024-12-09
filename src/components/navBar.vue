<template>
    <header>
        <nav>
            <router-link to="/">Home</router-link>
            <router-link to="/filmes">Filmes</router-link>
            <router-link to="/tv">Séries</router-link>
        </nav>
    </header>
</template>

<style scoped>
header {
    background-color: #2c3e50; /* Cor de fundo */
    color: #ffffff; /* Cor do texto */
    padding: 1rem;
    text-align: center;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.3); /* Sombra para dar profundidade */
}

nav {
    display: flex;
    justify-content: center; /* Centraliza os links */
    column-gap: 2rem;
}

nav a {
    text-decoration: none;
    color: #ffffff; /* Cor do texto dos links */
    font-weight: bold; /* Negrito para os links */
    transition: color 0.3s; /* Transição suave para a cor */
}

nav a:hover {
    color: #f39c12; /* Cor ao passar o mouse */
}
</style>