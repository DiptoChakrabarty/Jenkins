Explanation of each playbook

All  variables present in  vars/main.yml

## java.yml  && path.yml

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
JAVA_HOME="/usr/lib/jvm/java-1.8.0-openjdk-amd64"
export JAVA_HOME
PATH=$PATH:$JAVA_HOME

Add last 3 lines in .bashrc
```

## install_deb.yml

[Jenkins Repository Url for Debian Systems](https://pkg.jenkins.io/debian/)

```
Install dependencies to configure
Add Jenkins Repository to apt with key

- name: Add Jenkins apt repository key.
  apt_key:
    url: "{{ jenkins.deb_url_key }}"
    state: present
- name: get jenkins
  apt_repository:
        repo: "{{jenkins.deb_url}}"
        state: present

Install aptitute 
Update and Upgrade Server (needs aptitude)
- name: install aptitude
  apt:
      name: aptitude
      state: present

- name: update and upgrade packages
  apt:
      update_cache: yes
      name: "*"
      state: latest


Install Jenkins and enable it 

```

