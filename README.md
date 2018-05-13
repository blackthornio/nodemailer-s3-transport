# S3 Transport for Nodemailer

Applies for Nodemailer v1.x and not for v0.x where transports are built-in.

## Usage

Install with npm

    npm install nodemailer-s3-transport

Require to your script

```javascript
var nodemailer = require('nodemailer');
var pickupTransport = require('nodemailer-s3-transport');
```

Create a Nodemailer transport object

```javascript
var transporter = nodemailer.createTransport(pickupTransport(options))
```

Where

  * **options** defines connection data
     * **bucketName** - The S3 bucket name where applications save e-mail (required)
     * **bucketRegion** - The AWS region of the S3 bucket where applications save e-mail (required)
     * **accessKeyId**  - The AWS accessKeyId which has access to the S3 bucket
     * **secretAccessKey** - The AWS secretAccessKey which has access to the S3 bucket

  * `AWS_ACCESS_KEY_ID` and `AWS_SECRET_ACCESS_KEY` can also be used to set `accessKeyId` and `secretAccessKey`

**Example**

```javascript
var transport = nodemailer.createTransport(pickupTransport({
    bucketName: 'my-s3-bucket-name-here',
    bucketRegion: 'us-east-1',
    accessKeyId: 'your access key id',
    secretAccessKey: 'your secret access key',    
}));
```

## License

**MIT**


