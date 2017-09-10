在分布式系统中实现数据共享和文件上传下载

   1. 比如说之前单台tomcat服务器进行文件上传，可以指定文件并上传文件到指定路径
      现在要做多台机器的文件上传就需要单独把文件系统独立出来，通过ftp或者fastdfs提供的api进行文件的上传和下载
	  
   2. 同理，之前session在单台服务器可以通过request.getSession()获取，session.setAttribute和getAttribute把数据
      放到服务器内存中进行访问。
	  现在要做多台机器之间的session共享可以把session的信息存储到redis集群服务器中去，多台tomcat get和set都通过
	  访问redis集群去操作。做到多台tomcat都能访问同一个session
      