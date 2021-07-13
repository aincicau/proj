<template>
    <div v-if="firstName.indexOf('M') == 0" :id = "firstName">
        1. {{name}}
    </div>
    <div v-else :id = "firstName">
        2. {{name}}
    </div>
</template>

<script>
export default {
    name: 'Person',
    props: ['firstName', 'lastName'],
    data(){
        return {
            name: this.firstName + ' '+ this.lastName
        }
    },
    created(){
        console.log('Person was created');
    },
    mounted(){
        console.log('Person was mounted')
    }
}
</script>