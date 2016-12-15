# How 

<pre>
<code>
With fields:

curl --data "param1=value1&param2=value2" https://example.com/resource.cgi
Multipart:

curl --form "fileupload=@my-file.txt" https://example.com/resource.cgi
Multipart with fields and a filename:

curl --form "fileupload=@my-file.txt;filename=desired-filename.txt" --form param1=value1 --form param2=value2 https://example.com/resource.cgi
Without data:

curl --data '' https://example.com/resource.cgi

curl -X POST https://example.com/resource.cgi

curl --request POST https://example.com/resource.cgi
</code>
</pre>

# Reference

 - http://stackoverflow.com/questions/19116016/what-is-the-right-way-to-post-multipart-form-data-using-curl
 - http://superuser.com/questions/149329/what-is-the-curl-command-line-syntax-to-do-a-post-request
 - http://blog.csdn.net/xiaojianpitt/article/details/6856536