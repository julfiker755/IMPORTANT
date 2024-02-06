```js
 // Email Sending
// example url = http://localhost:3000/api/email?email=julfiker755.bd@gmail.com
import { NextResponse } from "next/server"
import nodemailer from 'nodemailer'

export const GET=async(req,res)=>{
    const {searchParams}=new URL(req.url)
    const toemail=searchParams.get("email")

    //  transporter
    let transporter = nodemailer.createTransport({
        host: "mail:teamrabbil.com",
        port: 25,
        secure: false,
        auth: {
          user: "info@teamrabbil.com",
          pass: "~sR4[bhaC[Qs",
        },
        tls:{rejectUnauthorized:false}
      });

    //  sendMail
    let myemail = await transporter.sendMail({
        from: '"Send the emai provider " <info@teamrabbil.com>', 
        to:toemail,
        subject: "Text nex js Email", 
        text: "Hello world ??", 
      });
  try{
    await transporter.sendMail(myemail)
    return NextResponse.json({message:'success email'})
  }catch(err){
    return NextResponse.json({message:'fail email'})
  }
   
}
```
