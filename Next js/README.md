```js
//css use
// post.module.css
```

```js
// domain set anathor domain use
/** @type {import('next').NextConfig} */
const nextConfig = {
    images:{
        domains:["images.pexels.com"]
    }
}

module.exports = nextConfig
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
****************NextConfig***************
const nextConfig = {
    basePath:'/submenu'
};

```

