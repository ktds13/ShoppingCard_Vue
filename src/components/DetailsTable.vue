<template>
<div>
    <!-- <table>
        <th>
            <td>Quantity</td>
            <td>Total Price </td>
            <td>asd</td>
        </th> -->
        <tr >
            <td>{{fruits.image}}</td>
            <td>{{fruits.name}}</td>
            <td>{{fruits.price}} </td>
            
        </tr>
        
    <!-- </table>
    <h1>{{total}} </h1> -->
</div>
</template>

<script>
export default {
    props:{
        fruits:{
            type: Array,
            required:true
        },
        total: {
            type: Number,
        }
    
    }
}
</script>