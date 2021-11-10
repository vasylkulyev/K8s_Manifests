# Use encode credentials in mongo-secret.yaml
$echo -n mongouser | base64 ==== ENCODING "mongouser"
$echo -n mongopassword | base64 ==== ENCODING "mongopassword"

# Steps:
$kubectl apply -f mongo-config.yaml ==== First start configmap
$kubectl apply -f mongo-sercret.yaml ==== Second start secrets
$kubectl apply -f mongo.yaml ==== Create Database
$kubectl apply -f webapp.yaml ==== Deploy Web-Application with MongoDB
