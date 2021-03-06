<h1>PHP heroku to AWS EC2 S3 SQS</h1>

<a href="https://heroku.com/deploy?template=https://github.com/PhyrexTsai/Heroku-AWS-EC2-S3-SQS-php.git">
<img src="https://camo.githubusercontent.com/c0824806f5221ebb7d25e559568582dd39dd1170/68747470733a2f2f7777772e6865726f6b7563646e2e636f6d2f6465706c6f792f627574746f6e2e706e67" alt="Deploy" data-canonical-src="https://www.herokucdn.com/deploy/button.png" style="max-width:100%;">
</a>

<h2>Introduction</h2>
This project use AWS EC2, S3, SQS to combine a image thumbnail ecosystem.<br>
1. Client upload an image file to S3.<br>
2. SQS request/response "inbox" queue from client to EC2.<br>
3. EC2 thumbnail the image file and push to S3.<br>
4. SQS request/response "outbox" queue to client.<br>

<h2>Setting application config vars</h2>
<div class="CodeRay">
  <div class="code"><pre><span class="prompt">$</span><span class="function"> heroku config:set AWS_ACCESS_KEY_ID=aaa AWS_SECRET_ACCESS_KEY=bbb S3_BUCKET=ccc
</span></pre></div>
</div>
Reference link to : [Heroku](https://devcenter.heroku.com/articles/s3-upload-php)<br>
<h2>Setting AWS Permission</h2>
At AWS you need to set "Users" > "Permission" > "Attach Policy" to let your account access the S3 project.<br>
"Attach Policy" must choose "AmazonS3FullAccess" and "AmazonSQSFullAccess".<br>
