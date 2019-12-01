Explanation of each playbook

## java.yml

```
- Remove Previous Version of Java
- Install Java-1.8
- Configure Java Path 
- Make the path permanent by adding an entry in .bashrc

```

* Configuring Java Path

```
java -version
find /usr/lib/jvm/java-1.8* | head -n 3
JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk-1.8.0.212.b04-1.el8_0.x86_64
export JAVA_HOME
PATH=$PATH:$JAVA_HOME

Add last 3 lines in .bashrc
```