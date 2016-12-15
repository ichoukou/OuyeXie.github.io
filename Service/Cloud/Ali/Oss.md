 - https://github.com/berwin/aliyun-oss-upload-stream
 
 - [OSS常见咨询问题](https://help.aliyun.com/knowledge_detail/39592.html)
    - 7、OSS 允许用户上传同名文件么？
      
      OSS允许用户上传同名的文件，这时是会对源文件直接进行覆盖操作。如果对文件唯一性有要求，您可以通过您的程序来实现唯一的文件名。也可以上传前检查下Object是否存在再进行上传操作。
      
    - [OSS 跨域资源共享（CORS）使用指南](https://help.aliyun.com/document_detail/31928.html)