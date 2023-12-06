# 使用官方的Jenkins基础镜像，该镜像已经包含了OpenJDK
FROM jenkins/jenkins:latest

# 切换到root用户
USER root

# 安装JDK 17，你可以根据需要选择其他版本
RUN apt-get update && \
    apt-get install -y openjdk-17-jdk && \
    rm -rf /var/lib/apt/lists/*

# 安装Node.js和npm
RUN curl -fsSL https://nodejs.org/dist/v14.17.3/node-v14.17.3-linux-x64.tar.xz -o node.tar.xz && \
    tar -xJf node.tar.xz -C /usr/local --strip-components=1 && \
    rm node.tar.xz

# 切换回Jenkins用户
USER jenkins

# 安装插件或其他Jenkins配置，根据你的需求进行修改


# 暴露Jenkins端口
EXPOSE 8080

# 设置Jenkins的home目录，可以根据需要进行修改
ENV JENKINS_HOME /var/jenkins_home

# 可选：设置Jenkins的一些参数，例如插件安装的默认选择等
ENV JAVA_OPTS -Djenkins.install.runSetupWizard=false