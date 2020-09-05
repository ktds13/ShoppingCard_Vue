<template>
<div>
    <table>
        <tr v-if="items.length">
            <td>
    <ItemList
    v-for="item in items"
    :key="item.id"
    :item="item"
    @add-item="onAddItem"

    />
    </td>
    </tr>
    </table>
    <table>
        <thead>
            <th> Image</th>
            <th> Name </th>
            <th> Price</th>
            <!-- <th> Total </th> -->
        </thead>
        <tbody>

            <ItemRow
            v-for="(fruit,i) in fruits"
           :key = i
           :fruit = "fruit"
          
             @remove-item="onRemoveItem"
            />
        </tbody>
    </table>

    <p> Total Cost: {{total}} </p>
    <p> Quantity : {{count}}</p>


    </div>
</template>

<script>
import ItemList from './ItemList'
import ItemRow from './ItemRow'
let itemId=1
export default {
    components:{
        ItemList,
        ItemRow
    },
    data(){
        return{
items:[
    {
        id: itemId++,
        name: 'Apple',
        image: require('../assets/apple.jpg'),
        alt: "Apple",
        price: 10
    },
    {
        id: itemId++,
        name: 'Orange',
        image: require('../assets/orange.jpg'),
        alt : "Orange",
        price:5
    },
     {
        id: itemId++,
        name: 'Melon',
        image: require('../assets/melon.jpg'),
        alt : "Melon",
        price:5
    },
     {
        id: itemId++,
        name: 'Papaya',
        image: require('../assets/papaya.jpg'),
        alt : "Papaya",
        price:5
    },
     {
        id: itemId++,
        name: 'Pineapple',
        image: require('../assets/pineapple.jpg'),
        alt : "Pineapple",
        price:5
    },
     {
        id: itemId++,
        name: 'Strawberry',
        image: require('../assets/strawberry.jpg'),
        alt : "Strawberry",
        price:5
    },
     {
        id: itemId++,
        name: 'Watermelon',
        image:require("../assets/watermelon.jpg"),
        alt : "Watermelon",
        price:5
    },



],

total : 0,
count : 0,
qty : 0,
fruits: []
   }
    },
methods: {
  onRemoveItem (product) {
    this.total -= product.price
    this.count--

   this.fruits.pop(product)
  },
onAddItem (product){
   this.total += product.price
   this.count++

  this.fruits.push(product)
}
}
        }


</script>