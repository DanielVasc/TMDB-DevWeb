<script setup>
import { defineProps, onMounted } from 'vue';
import { useTvStore } from '@/stores/tv';
const tvStore = useTvStore();

const props = defineProps({
    tvId: {
        type: Number,
        required: true,
    },
});

onMounted(async () => {
    try {
        await tvStore.getTvDetail(props.tvId);
    } catch (error) {
        console.error("Erro ao carregar detalhes da série:", error);
        
    }
});
</script>

<template>
    <div class="main">
        <div class="content">
            <img :src="`https://image.tmdb.org/t/p/w185${tvStore.currentTv.poster_path}`" :alt="tvStore.currentTv.title" class="poster" />
            <div class="details">
                <h1>Série: {{ tvStore.currentTv.original_name }}</h1>
                <p class="tagline">{{ tvStore.currentTv.tagline }}</p>
                <p class="overview">{{ tvStore.currentTv.overview }}</p>
                <p>Avaliação: <span class="rating">{{ tvStore.currentTv.vote_average }}</span></p>
            </div>
        </div>

        <h2>Produtoras</h2>
        <div class="companies">
            <template v-for="company in tvStore.currentTv.production_companies" :key="company.id">
                <img v-if="company.logo_path" :src="`https://image.tmdb.org/t/p/w92${company.logo_path}`" :alt="company.name" class="company-logo" />
                <p v-else>{{ company.name }}</p>
            </template>
        </div>
    </div>
</template>

<style scoped>
.main {
    padding: 20px;
}

.content {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-bottom: 20px;
}

.poster {
    width: 185px;
    height: auto;
    border-radius: 8px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
}

.details {
    text-align: center;
    margin-top: 15px;
}

.tagline {
    font-style: italic;
    color: #666;
}

.overview {
    margin: 10px 0;
}

.rating {
    font-weight: bold;
}

.companies {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    margin-top: 20px;
}

.company-logo {
    width: 92px;
    height: auto;
    margin: 0 10px;
}
</style>