<template>
    <div class="card">
        <img :src="image" height="280">
    </div>
</template>

<script>
export default {
    name:'Card',
    props:{
        number:Number,
        suit:String,
        hide:Boolean
    },
    computed:{
        image:()=>{
            const filename = this.hide ? 'CardBack' : `${this.suit}_${this.number.toString().padStart(2, '0')}`
            return require(`~/assets/${filename}.png`)
        }
    }
}
</script>