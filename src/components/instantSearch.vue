<template>
    <div>
        <h1>V model in text area</h1>
        <textarea name="" id="" cols="80" rows="5" v-model="message"></textarea>
        <h2 style="white-space: pre-line">{{message}}</h2>

        <h1>Instant Search demonstration</h1>
        <input type="text" v-model="search">
        <article v-for="post in filteredPost" :key="post.id">
           <h1> {{post.title}} </h1>
           <h5> {{post.description}} </h5>
        </article>

    </div>
</template>
<script>
export default {
    name:'instantSearch',
    data(){
        return{
            message:'type here',
            search:'',
            posts:[
                {id:1,title:'urran',description:'this is description of post 1'},
                {id:2,title:'post2',description:' digital this is description of post 2'},
                {id:3,title:'post3',description:'this is description of post 3'},
                {id:4,title:'post4',description:'this is description of post 4'},
                {id:5,title:'post5',description:'this is description of post 5'},
                {id:6,title:'post6',description:'this is description of post 6'},
                {id:7,title:'post7',description:'this is description of post 7'},
                {id:8,title:'post8',description:'this is description of post 8'},
                {id:9,title:'post9',description:'this is description of post 9'},
                {id:10,title:'post10',description:'this is description of post 10'}
            ]
        }
    },
    computed:{
        filteredPost(){
            // if(this.title == true){
            // return this.posts.filter(post => post.description.toLowerCase().includes(this.search.toLowerCase()))
            // }
            // else if(this.description == true){
            // return this.posts.filter(post => post.title.toLowerCase().includes(this.search.toLowerCase()))
            // }
            // else{
            //     return console.log("the search is not present")
            // }  


            
            // return [
            //  this.posts.filter(post => post.title.toLowerCase().includes(this.search.toLowerCase())),
            //  this.posts.filter(post => post.description.toLowerCase().includes(this.search.toLowerCase()))
            // ]


    return (this.posts.filter(post => post.title.toLowerCase().includes(this.search.toLowerCase()))) != "" ? (this.posts.filter(post => post.title.toLowerCase().includes(this.search.toLowerCase()))) : (this.posts.filter(post => post.description.toLowerCase().includes(this.search.toLowerCase())))

            // if(this.post.title != null){
            // alert("title");
            // // return this.posts.filter(post => post.title.toLowerCase().includes(this.search.toLowerCase())) 
            // }
            // else if(this.post.description != null){
            // alert("desc");

            // // return this.posts.filter(post => post.description.toLowerCase().includes(this.search.toLowerCase()))
            // }
            // else{
            //     // return console.log("the search is not present")
            // } 


            // return ((this.posts.filter(post => post.title.toLowerCase().includes(this.search.toLowerCase()))) || (this.posts.filter(post => post.description.toLowerCase().includes(this.search.toLowerCase())) ))





            
        }
    }
}
</script>