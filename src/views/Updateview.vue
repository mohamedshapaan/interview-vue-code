<template>
    <h1>AddView</h1>
    <form @submit.prevent="Updatefun">
        <div class="form-group">
            <label>arrivingArabicName</label>
            <input type="text" class="form-control" v-model="arrivingArabicName">
            
        </div>
        <div class="form-group">
            <label>arrivingEnglishName</label>
            <input type="text" class="form-control" v-model="arrivingEnglishName">
            
        </div>
        <div class="form-group">
            <button type="submit" class="btn btn-primary">add</button>
            
        </div>
        
    </form>
    </template>
    <script>
    export default{
        name:"Update",
        data(){
            return{
                arrivingArabicName:"",
                arrivingEnglishName:""
            };
        },
        methods:{
            Updatefun(){
                const instance = axios.create({
      baseURL: 'http://40.127.194.127:777/api/',
      timeout: 1000,
      headers: {'Authorization': 'Bearer '+ "eyJhbGciOiJodHRwOi8vd3d3LnczLm9yZy8yMDAxLzA0L3htbGRzaWctbW9yZSNobWFjLXNoYTI1NiIsInR5cCI6IkpXVCJ9.eyJodHRwOi8vc2NoZW1hcy54bWxzb2FwLm9yZy93cy8yMDA1LzA1L2lkZW50aXR5L2NsYWltcy9uYW1lIjoic3VwZXJhZG1pbiIsImh0dHA6Ly9zY2hlbWFzLnhtbHNvYXAub3JnL3dzLzIwMDUvMDUvaWRlbnRpdHkvY2xhaW1zL3NpZCI6IjAwMDdjYWY1LWFjNjktNDViNi1hOTA1LWI1NjBlNTkxOWI4OSIsImRvY3RvcklkIjoiMCIsImV4cCI6MTY3ODAwNDE5OCwiaXNzIjoiQ2xpbml2aXNvciIsImF1ZCI6IkNsaW5pdmlzb3IifQ.tiFn3FA8FmD46pl55c95c-W00dQlV-G8LvUVUDKptos"}
    });
    
    instance.post('Emergency/AddOrUpdateArrivingMethod',
    {
        arrivingArabicName:this.arrivingArabicName,
        arrivingEnglishName:this.arrivingEnglishName
    }
    )
    .then(response => {
        console.log(response);;
    })
            }
        }
    }
    import axios from "axios";
    
    </script>