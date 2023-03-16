<template>
    <div>
        <h1>My Login Data</h1>
        <p> here is userid: {{ content[0].userid }}</p>
        <p> here is firsttname: {{ content[0].firstname }}</p>
    </div>

</template>
<script>
    import { useSanityFetcher } from 'vue-sanity'
    const user = "swirth9092"

    export default {
    data () {
        return {
            loading: true,
        }
    },

    setup() {

        //// update to a nmount component so no render issues....  
        const {data: content } = useSanityFetcher(`*[userid == "${user}"]`) 
        return {content}

        //   // const {data: content } = useSanityFetcher(
        //   //   () => `*[_type=="user" && userid==${user}{
        //   //     _id,
        //   //     userid
        //   //   }`
        // const { color, size, gender } = selection // { color: "Red", size: "Small", gender: "Female" }
        // const query = `*[color == "${color}" && size == "${size}" && gender == "${gender}"]`

        //   const {data: content } = useSanityFetcher("*[userid == 'swirth9092']") 
//   return {content}
}

    // created() {
    //     this.fetchData();
    // },
    // methods: {
    //     urlFor(source) {
    //         return  builder.image(source)
    //     },
    //     fetchData() {
    //         this.error = this.LoginForm = null;
    //         this.loading = true;
    //         sanity.fetch(query).then(
    //             (content) => {
    //                 this.loading = false;
    //                 this.content = content;
    //             },
    //             (error) => {
    //                 this.error = error;
    //             }
    //         );
    //     },
    // },
    }
</script>
<style>
    
</style>