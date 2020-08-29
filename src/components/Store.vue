<template>
<div>
    <table>
        <tr v-if="items.length">
            <td>
    <ItemList
    v-for="item in items"
    :key="item.id"
    :item="item"
    v-on:add-item="total += $event"
     v-on:remove-item="total -= $event"
    />
    </td>
    </tr>
    </table>
    <!-- <DetailsTable
    v-bind= "total"
  
    /> -->
    <!-- <p> Quantity : {{item.length}} </p> -->
    <p> Total Cost: {{total}} </p>
    </div>
</template>

<script>
import ItemList from './ItemList'
//import DetailsTable from './DetailsTable'
let itemId=1
export default {
    components:{
        ItemList,
       // DetailsTable
    },
    data(){
        return{
items:[
    {
        id: itemId++,
        name: 'Apple',
        image: '../assets/apple.png',
        alt: "Apple",
        price: 10
    },
    {
        id: itemId++,
        name: 'Orange',
        image:'../assets/orange.jpg',
        alt : "Orange",
        price:5
    },
     {
        id: itemId++,
        name: 'Melon',
        image:'../assets/melon.jpg',
        alt : "Melon",
        price:5
    },
     {
        id: itemId++,
        name: 'Papaya',
        image:'./assets/papaya.jpg',
        alt : "Papaya",
        price:5
    },
     {
        id: itemId++,
        name: 'Pineapple',
        image:'../assets/pineapple.jpg',
        alt : "Pineapple",
        price:5
    },
     {
        id: itemId++,
        name: 'Strawberry',
        image:'../assets/strawberry.jpg',
        alt : "Strawberry",
        price:5
    },
     {
        id: itemId++,
        name: 'Watermelon',
        image:"../assets/watermelon.jpg",
        alt : "Watermelon",
        price:5
    },
    

    
],
total : 0,
// methods: {
//   onRemoveItem: function (cost) {
//     this.total -= cost
//   }
// }
        }
    }
}
</script>