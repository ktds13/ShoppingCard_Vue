<template>
    <div>
        <div class="product-image">
       <img :alt=item.alt :src=item.image>
        </div>
        <div class="product-info">
    Item Name: {{item.name}} <br/>
    Price : {{item.price}} <br>
        </div>
        <button @click="$emit('add-item', item.price)">Add</button> 
    <button @click="$emit('remove-item', item.price)"> Remove</button>


    </div>
</template>

<script>
export default {
    props:{
        item:{
            type: Object,
          required:true
        }
    }
    
}
</script>