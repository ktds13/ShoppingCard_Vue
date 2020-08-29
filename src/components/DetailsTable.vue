<template>
    <table>
        <th>
            <td>Quantity</td>
            <td>Total Price </td>
        </th>
        <tr>
            <td>{{item.len}}</td>
            <td>{{total}}</td>
            
        </tr>
        
    </table>
</template>

<script>
export default {
    props:{
        item:{
            type: Object,
            required:true
        },
        total: {
            type: Number,
            
        }
    }
}
</script>