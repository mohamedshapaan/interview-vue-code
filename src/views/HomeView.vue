<template>
<div v-for="item in list" :key="item.id" class="card" style="width: 18rem;">
  <div class="card-body">
    <h5 class="card-title">{{item.id}}</h5>
    <h6 class="card-subtitle mb-2 text-muted">{{item.accountId}}</h6>
    <p   class="card-link">{{item.arrivingEnglishName}}</p>
    <p   class="card-link">{{item.arrivingArabicName}}</p>
    <hr/>
    <button v-on:click="DELETE(item.id)">delete</button>
  </div>
</div>
</template>
<script>
export default{
    name:"home"
    data(){
    return{
      list: []
    }
  }
  metthods:{
    DELETE(id){
            const instance = axios.create({
  baseURL: 'http://40.127.194.127:777/api/',
  timeout: 1000,
  headers: {'Authorization': 'Bearer '+ "eyJhbGciOiJodHRwOi8vd3d3LnczLm9yZy8yMDAxLzA0L3htbGRzaWctbW9yZSNobWFjLXNoYTI1NiIsInR5cCI6IkpXVCJ9.eyJodHRwOi8vc2NoZW1hcy54bWxzb2FwLm9yZy93cy8yMDA1LzA1L2lkZW50aXR5L2NsYWltcy9uYW1lIjoic3VwZXJhZG1pbiIsImh0dHA6Ly9zY2hlbWFzLnhtbHNvYXAub3JnL3dzLzIwMDUvMDUvaWRlbnRpdHkvY2xhaW1zL3NpZCI6IjAwMDdjYWY1LWFjNjktNDViNi1hOTA1LWI1NjBlNTkxOWI4OSIsImRvY3RvcklkIjoiMCIsImV4cCI6MTY3ODAwNDE5OCwiaXNzIjoiQ2xpbml2aXNvciIsImF1ZCI6IkNsaW5pdmlzb3IifQ.tiFn3FA8FmD46pl55c95c-W00dQlV-G8LvUVUDKptos"}
});

instance.post('Emergency/DeleteArrivingMethod/'+id)
.then(response => {
    console.log(response);;
})
        }
  }
    async  mounted(){
    const instance = axios.create({
  baseURL: 'http://40.127.194.127:777/api/',
  timeout: 1000,
  headers: {'Authorization': 'Bearer '+ "eyJhbGciOiJodHRwOi8vd3d3LnczLm9yZy8yMDAxLzA0L3htbGRzaWctbW9yZSNobWFjLXNoYTI1NiIsInR5cCI6IkpXVCJ9.eyJodHRwOi8vc2NoZW1hcy54bWxzb2FwLm9yZy93cy8yMDA1LzA1L2lkZW50aXR5L2NsYWltcy9uYW1lIjoic3VwZXJhZG1pbiIsImh0dHA6Ly9zY2hlbWFzLnhtbHNvYXAub3JnL3dzLzIwMDUvMDUvaWRlbnRpdHkvY2xhaW1zL3NpZCI6IjAwMDdjYWY1LWFjNjktNDViNi1hOTA1LWI1NjBlNTkxOWI4OSIsImRvY3RvcklkIjoiMCIsImV4cCI6MTY3ODAwNDE5OCwiaXNzIjoiQ2xpbml2aXNvciIsImF1ZCI6IkNsaW5pdmlzb3IifQ.tiFn3FA8FmD46pl55c95c-W00dQlV-G8LvUVUDKptos"}
});

instance.get('/Emergency/GetAllArrivingMethods?first=0&page=0&rows=10')
.then(response => {
    this.list=response.data;
})

  }
  
    import axios from "axios";
}
</script>