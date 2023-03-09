<template>
    <header>
        <div class="logo">
            <img src="/images/pizza-logo.jpg"/>
            <h1>Papa Jonny's Pizza</h1>
        </div>
        <div class="tagline">
            <h2>Better Web Architecture.<br/>Better Web Apps.</h2>
        </div>
    </header>
</template>

<style>
    header {
        margin: 1rem auto;
        text-align: center;
    }
    header .logo {
        display: flex;
        justify-content: center;
    }
    header .logo img {
        max-width: 100px;
    }
    header .tagline {
        background-image: url('/images/Large-3-Topping.png');
        background-repeat: no-repeat;
        background-position: right;
        padding: 4rem 0rem;
    }
    header .tagline h2 {
        color: #c50000;
        padding: 1rem;
        margin: 0rem;
        text-align: left;
        background-color: #ffffff;
    }
    @media screen and (min-width: 670px) {
        header .tagline {
            background-size: contain;
        }
        header .tagline h2 {
            background-color: transparent;
        }
    }
    @media screen and (min-width: 1024px) {
        header .logo {
            justify-content: left;
        }
        header .tagline {
            background-size: cover;
        }
        header .tagline h2 {
            font-size: 1.75rem;
        }
    }
    @media screen and (min-width: 1500px) {
        header .tagline h2 {
            font-size: 2.25rem;
        }
    }
</style>