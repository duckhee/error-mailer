#error-mailer

Sent Error directly to developers


## Usage 

    
    //initial setup
    var errorMailer = require("error-mailer");
    var mailOptions        = {
     host       : 'smtp.gmail.com',
       user     : 'your_smtp_user_name,
       password : 'your_password',
       from     : 'app from email address',
       ssl      : true,
       port     : 465,
       to       : "your_email_address",
       domainName:  "The App Domain Name"
    };
    errorMailer.configureOptions(mailOptions);


   ### Now use from where exception is handled
   
       process.on('uncaughtException', function (err) {
         util.log('Caught exception: ');
         if (err.getStack) {
           util.log(err.getStack());
         } else {
           util.log(err);
         }
         //sent mail alert to the developer
         errorMailer.alert(err);
       });
   
      
      
    
    
    
    
    
## Credits

      - [Sajib Sarkar](http://github.com/thebapi)

## License

    The MIT License (MIT)

    Copyright (c) 2013 Sajib Sarkar

    Permission is hereby granted, free of charge, to any person obtaining a copy of
    this software and associated documentation files (the "Software"), to deal in
    the Software without restriction, including without limitation the rights to
    use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of
    the Software, and to permit persons to whom the Software is furnished to do so,
    subject to the following conditions:

    The above copyright notice and this permission notice shall be included in all
    copies or substantial portions of the Software.

    THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
    IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS
    FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
    COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
    IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
    CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

    
  
  
 

