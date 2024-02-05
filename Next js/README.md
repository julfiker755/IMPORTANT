```js
//css use
// post.module.css
```

```js
//{cache:'no-store'}
//{ cache: 'force-cache' }
//{next:{revalidate:5}}
const res=await fetch("http://localhost:2000/data", { cache: 'no-cache'})
const postdaa=await res.json()
````
```js
//map.slice(0,10) use limit for use
export async function generateStaticParams() {
  const res=await fetch("http://localhost:2000/data")
  const postdaa=await res.json()
  const ids=postdaa.map(d=>{
    return {
      id:d.id+""
    }
  })
  return ids
  // return [{ id: '1' }, { id: '2' }]
}
```
```js
//****************NextConfig***************

// images --
const nextConfig = {
    images:{
        domains:["images.pexels.com"]
    }
}


// base path --
const nextConfig = {
    basePath:'/submenu'
};

// env file --
const nextConfig = {
    env:{
        API_KEY:'fjfjdlfjdl'
    }
};

// headers --
const nextConfig = {
   async headers(){
     return [
        // {source:'/product',headers:[{key:'my-value',value:'123434'}]}
        {source:'/:path*',headers:[{key:'my-value',value:'123434'}]}
     ]
   }
};

```

