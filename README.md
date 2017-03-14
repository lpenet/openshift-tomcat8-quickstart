
## Quickstart to run Apache Tomcat 8.5 on OpenShift

Apache Tomcat 8.5 adds support for lots of Java EE 7 features like WebSockets, Servlet 4, JSP 2.3, Expression Language 3.0, as well as additional Tomcat-specific features.
It also borrows features from the forthcoming Tomcat 9, such as HTTP/2 and virtual hosts

1. First create an OpenShift DIY application with your desired appname (here, using "tomcat85"):
```
rhc app create tomcat85 diy
```

2. Add git remote to Tomcat 8 OpenShift quickstart and pull code from it.
```
cd tomcat85
git remote add upstream https://github.com/lpenet/openshift-tomcat85-quickstart.git
git pull -s recursive -X theirs upstream master
```
If you get an error saying ```fatal: refusing to merge unrelated histories``` use
```
git pull -s recursive -X theirs upstream master --allow-unrelated-histories
```
3. Push the code to OpenShift. 
```
git push
```

4. Check that Apache Tomcat 8.5 is up and running by going to http://tomcat85-{domain}.rhcloud.com. Replace {domain} with your own domain name.

5. Tomcat's examples will also be deployed. You can view them under http://tomcat85-{domain}.rhcloud.com/examples.
