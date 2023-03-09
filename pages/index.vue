<template>
    <main>
        <h3 id="subheader">{{ tagline }}</h3>
        <ul id="pizzaList">
            <li v-for="pizza in pizzas.data">
                <img alt="Pizza" src="/images/pizza-icon.jpg">
                <div class="pizza-info">
                    <h3>{{ pizza.name }}</h3>
                    <h4>Price: <span>${{ pizza.price }}</span></h4>
                </div>
            </li>
        </ul>
    </main>
</template>

<script setup>
    const runtimeConfig = useRuntimeConfig()
    const { data: pizzas } = await useLazyFetch(runtimeConfig.public.apiUrl + '/pizzas')
    const tagline = computed(() => pizzas == null ? 'Loading Pizzas...' : 'Checkout our Pizzas!')
</script>

<style>
    h3#subheader {
        text-align: center;
    }
    ul {
        list-style: none;
        padding: 0rem;
        width: 100%;
    }
    li {
        display: flex;
        flex-direction: column;
        width: 100%;
        text-align: center;
    }
    img {
        width: 100%;
        max-height: 300px;
        object-fit: contain;
    }
    @media screen and (min-width: 1024px) {
        li {
            flex-direction: row;
            justify-content: center;
        }
        img {
            max-width: 300px;
        }
        .pizza-info {
            display: flex;
            flex-direction: column;
            justify-content: center;

        }
    }
</style>