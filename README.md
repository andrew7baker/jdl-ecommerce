### 1 确认版本

    jhipster --version
    INFO! Using JHipster version installed globally
    6.2.0

### 2 先看下生成后的启动效果

![mpGOSg.png](https://s2.ax1x.com/2019/08/12/mpGOSg.png)

### 3 clone项目

    git clone --recursive https://github.com/andrew7baker/jdl-ecommerce.git
    cd jdl-ecommerce/notification
    ./mvnw -Pprod verify jib:dockerBuild -Dmaven.test.skip=true
    cd ../jdl-ecommerce/invoice
    ./mvnw -Pprod verify jib:dockerBuild -Dmaven.test.skip=true
    cd ../jdl-ecommerce/notification
    ./mvnw -Pprod verify jib:dockerBuild -Dmaven.test.skip=true
    cd ../docker-compose-no-es
    docker-compose up -d

    如果要自己重新生成 store、invoice、notification三个项目则23
    ➜  jdl-ecommerce git:(master) ✗ jhipster import-jdl microservice-ecommerce-store.jdl

### 4 docker-compose 生成步骤

![mptFsJ.png](https://s2.ax1x.com/2019/08/12/mptFsJ.png)

[微服务生成步骤](https://medium.com/jhipster/create-full-microservice-stack-using-jhipster-domain-language-under-30-minutes-ecc6e7fc3f77)

#### git submodule

    git submodule add https://github.com/andrew7baker/invoice.git invoice
    git submodule add https://github.com/andrew7baker/notification.git notification
    git submodule add https://github.com/andrew7baker/store.git store

[另一篇](https://blog.avenuecode.com/building-a-microservice-in-20-minutes-with-jhipster)