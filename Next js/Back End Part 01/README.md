```js
 // Working With URL Params [ Request ]

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

```js
 // Working With Form Data [Request]

export const POST=async(req,res)=>{
    const fromdata=await req.formData()
    const gender=fromdata.get("gender")
    const phone=fromdata.get("phone")
    return NextResponse.json({status:'success',gender:gender,phonenum:phone})
}
```
```js
 // Working With Headers [Request]

export const GET=async(req,res)=>{
    const headerslist=headers()
    const api_key=headerslist.get('API_KEY')
    return NextResponse.json({status:'success',message:api_key})
}
```
```js
 // Working With Cookies [Request]

export const GET=async(req,res)=>{
     // const token=req.cookies.get('token')['name']
    // const token=req.cookies.get('token')['value']
    const token=req.cookies.get('token')
    return NextResponse.json({status:'success',message:token})
}

```
```js
 // Working With Status Code [Response]  -- 
export const GET=async(req,res)=>{
    return NextResponse.json(
        // {body}{status}
        {roll:'404420',name:'julfiker'},
        {
            status:203
        }
        )
}

```

