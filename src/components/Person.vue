<template>
    <div :id = "firstName">
        {{name}}
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