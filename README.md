# foo-tf, simple tensorflow projects


### 一、开发环境搭建  
1. dockerfile 说明:  
  dockerfiles/Dockerfile.dev 是在 tensorflow/tensorflow:latest-jupyter 的基础上加入了ssh 的功能，从而支持 visual studio code 远程连接.  
  dockerfiles/Dockerfile.dev-gpu 是在dockerfiles/Dockerfile.dev的基础上加入了对gpu的支持.  

2. 启动开发环境的docker 镜像:  
```
  chmod a+w -R /data/foo-tf  
  docker run -it -v /data/foo-tf/:/home/foo-tf/workspace/ -p 34567:8888 -p 34568:22 debugman007/tf-dev:latest  
```

3. vscode 中配置  
   vscode 通过 ssh-remote 插件连接开发环境的docker 镜像(默认ssh账号和密码为 foo-tf:foo-tf)后，可以进行开发;    
   vscode 中通过 jupyter notebook插件可以进行jupyter notebook的开发和使用，配置jupyter notebook插件的时候,设置jupyter server地址为 开发环境镜像内部的notebook地址 (http://localhost:8888/?token=xxxxx)  

### 二、tutorial  
1. tutorial/classification.ipynb 为一个对图片进行多分类的任务.  
2. tutorial/classification-advance.ipynb 自定义model class 来完成图片多分类任务.  

