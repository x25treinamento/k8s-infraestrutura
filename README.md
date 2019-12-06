# Infraestrutura Kubernetes

Infraestrutura de DevOps no Kubernetes que utilizamos na X25 Treinamento e Consultoria.

## Recursos 
- Jenkins no kubernetes
- Helm
- IBM Cloud

### Jenkins no Kubernetes

Antes de executar os seguintes comandos abaixo, verifique se os seguintes passos foram executados:

1. Cluster kubernetes devidamente criado;
2. Kubernetes cliente instalado e devidamente configurado;
3. Helm devidamente instalado e repositorio devidamente adiconado;
4. IBM Cloud CLI devidamente instalado (Se o cluster foi criado na IBM Cloud);

Para realizar o deploy do jenkins customizamos alguns valores, então para instalar o jenkins no seu cluster execute o seguinte comando:

`   $    helm install jenkins stable/jenkins -f jenkins/helm/values.yalm
`

Para recuperar a senha do usuário admin execute o seguinte comando:

`$   printf $(kubectl get secret --namespace default jenkins -o jsonpath="{.data.jenkins-admin-password}" | base64 --decode);echo`


