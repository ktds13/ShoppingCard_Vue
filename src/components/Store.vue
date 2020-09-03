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
     @remove-item="onRemoveItem"
    />
    </td>
    </tr>
    </table>
    <table>
        <tbody>
            <DetailsTable
            :fruits = "fruits"
            />
        </tbody>
    </table>
    <!-- <DetailsTable
  :total = "total"
  :fruits = "fruits"
    /> -->
    <!-- <p> Quantity : {{item.length}} </p> -->
    <p> Total Cost: {{total}} </p>
    <p> Quantity : {{count}}</p>
    </div>
</template>

<script>
import ItemList from './ItemList'
import DetailsTable from './DetailsTable'
let itemId=1
export default {
    components:{
        ItemList,
        DetailsTable
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
            fruits: []
        }
    },
    methods: {
          onRemoveItem (product) {
            this.total -= product.price
            this.count--
          },
        onAddItem (product){
           this.total += product.price
           this.count++
           let productId = 0
            this.fruits = new product({
               id: productId++,
                name: product.name,
                image: product.image,
                alt : product.alt,
                price:product.price
           })
        }
    }
}
    

</script>
