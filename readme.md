#Gitlab-runner

访问仓库配置 http://YOURGITLABDOMAIN.com/PROJECT_NAME/settings/ci_cd
获取注册 runner 所需要的 url 和 token

分别更新到 configmap.yml, secret.yml, **可能需要替换namespace cicd-k8s
为对应的值**

```
$ echo $TOKEN | base64 -w0
```

分别创建好所需的配置后就可以在项目配置页发现并启动 runner

```
kubectl apply -f secret.yml
kubectl apply -f configmap.yml
kubectl apply -f register.yml
kubectl apply -f runner.yml
```
