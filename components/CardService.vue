<template>
    <nuxt-link :to="`${path}/${param}`">
        <div class="py-5 card-service bg-green-400 rounded-lg shadow-xl">
            <img class="img-service" :src="url" alt="">
            <p class="name-service">{{name}}</p>
        </div>
    </nuxt-link>
</template>

<script>
export default {
    props:{
        url: {
            type: String,
            default: ''
        },
        name:{
            type: String,
            default: ''
        },
        path:{
            type: String,
            default: ''
        },
        param:{
            type: String,
            default: ''
        }
    }
}
</script>

<style>
.card-service{
    height: 300px;
    width: 250px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    box-shadow: 10px 10px 19px -8px rgba(0,0,0,0.75);
    -webkit-box-shadow: 10px 10px 19px -8px rgba(0,0,0,0.75);
    -moz-box-shadow: 10px 10px 19px -8px rgba(0,0,0,0.75);
}

.types-services{
    display: flex;
    flex-direction: column;
    align-items: center;
}

.img-service{
    height: 110px;
}

.name-service{
    color: white;
    margin-top: 20px;
    font-size: 22px;
    text-align: center;
    font-weight: bold;
}

.card-service:hover{
    transition: .6s;
    transform: scale(1.03);
}

@media (max-width: 900px) {
    .card-service{
        height: 200px;
        width: 150px;
    }

    .img-service{
        height: 80px;
    }

    .name-service{
        font-size: .8rem;
    }
}
</style>