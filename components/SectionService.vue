<template>
    <div class="card-my-service express flex rounded-lg mt-8 border-2 shadow-lg">
      <div :class="index%2 == 0 ? 'order-2':'order-1 rounded-tl-lg'" class="container-img">
        <img :class="index%2 == 0 ? 'rounded-r-lg':'rounded-l-lg'" class="img-service font-thin" src="/male-courier.jpg" alt="" width="100%">
      </div>
      <div :class="index%2 == 0 ? 'order-1':'order-2'" class="container-description p-8 text-center flex flex-col items-center justify-center">
        <p class="text-2xl font-light mb-3">{{name}}</p>
        <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. In maiores harum alias nesciunt magni sapiente debitis illo suscipit rem nam cumque non, vero reprehenderit minima labore cum. Assumenda, unde provident.</p>
        <a href="#form-ask" class="btn-sol-information bg-green-400 text-white shadow-xl w-52 rounded-md mt-6">
          Solicitar informacion 
        </a>
      </div>
    </div>
</template>

<script>

export default {
    props:{
        name:{
            type: String,
            default: ''
        },
        index:{
            type: Number,
            default: 0
        },
        url:{
            type: String,
            default: ''
        }
    }
}
</script>

<style scoped>
*{
    box-sizing: border-box
}
.container-description{
    width: 65%;
}

.container-img{
    width: 35%;
    height: 100%;
}
.img-service{
    width: 100%;
    height: 100%;
}

.card-my-service{
  width: 70%;
  height: 300px;
}

.btn-sol-information{
    display: flex;
    align-items: center;
    justify-content: center;
    height: 40px;
}

@media (max-width: 900px) {
    .card-my-service{
        height: 15rem;
        font-size: .7rem;
    }
    
    .btn-sol-information{
        height: 60px;
        padding: 5px;
        width: 130px;
    }
}
</style>