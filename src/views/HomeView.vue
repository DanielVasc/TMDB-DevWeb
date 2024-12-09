<script setup>

</script>

<template>
    <div>
        <h1>Home</h1>
    </div>

</template>

<style scoped>
.header {
    background-color: var(--vt-c-indigo);
    color: var(--color-background);
    padding: 1rem;
    text-align: center;
}

.featured-section {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin: 2rem 0;
}

.featured-title {
    font-size: 2rem;
    margin-bottom: 1rem;
}

.featured-list {
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
    gap: 1rem;
}

.featured-item {
    width: 20rem;
    border-radius: 0.5rem;
    overflow: hidden;
    box-shadow: 0 0 0.5rem #000;
    transition: transform 0.3s; /* Transição suave */
}

.featured-item:hover {
    transform: scale(1.05); /* Efeito de zoom ao passar o mouse */
}

.featured-item img {
    width: 100%;
    height: 15rem;
    border-radius: 0.5rem;
}

.featured-description {
    padding: 0.5rem;
    text-align: center;
}
</style>