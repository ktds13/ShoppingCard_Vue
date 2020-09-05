<template>
<div>
    
        <tr >
            <td> <img :alt=fruit.alt :src=fruit.image></td>
            <td>{{fruit.name}}</td>
            <td>{{fruit.price}} </td>
            <!-- <td>{{total}} </td> -->
            <td>  <button @click="$emit('remove-item', fruit)"> Remove</button>
</td>
            
        </tr>
        
   
</div>
</template>

<script>
export default {
    props:{
        fruit:{
            type: Object,
            required:true
        },
        // total:{
        //     type: Number,
        //     required : true
        // }
       
    }
}
</script>