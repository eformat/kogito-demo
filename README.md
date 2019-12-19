# kogito-demo

The Kogito Developer Workflow
- https://porcelli.me/announcement/tooling/vscode/bpmn/2019/09/11/new-vscode-gui-editor.html

Bootstrap code
```
mvn io.quarkus:quarkus-maven-plugin:0.21.2:create \
     -DprojectGroupId=org.acme \
     -DprojectArtifactId=using-kogito \
     -Dextensions="kogito"
```

Loacally
```
mvn compile quarkus:dev
```

OpenShift
```
oc login
oc new-project kogito
kogito use-project kogito
kogito deploy kogito-persons https://github.com/eformat/kogito-demo.git
```

Test
```
curl -X POST http://localhost:8080/persons \
     -H 'content-type: application/json' \
     -H 'accept: application/json' \
     -d '{"person": {"name":"John Quark", "age": 20}}'

curl -X POST http://localhost:8080/persons \
     -H 'content-type: application/json' \
     -H 'accept: application/json' \
     -d '{"person": {"name":"John Quark", "age": 30}}'
```