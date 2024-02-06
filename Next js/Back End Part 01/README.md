```js
 // Working With URL Params

//example---  http://localhost:3000/api/menu?id=1000
export const GET=async(req,res)=>{
    const {searchParams}=new URL(req.url)
    const idvalue=searchParams.get("id")
    return NextResponse.json({status:'success',message:idvalue})
}

//example---  http://localhost:3000/api/menu?id=1000](http://localhost:3000/api/menu?id=1000&roll=404428)
export const GET=async(req,res)=>{
    const {searchParams}=new URL(req.url)
    const idvalue=searchParams.get("id")
    const roll=searchParams.get("roll")
    return NextResponse.json({status:'success',roll:roll,id:idvalue})
}

```
