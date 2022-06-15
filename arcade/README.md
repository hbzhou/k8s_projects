# arcade game
## 1.port foward with ingress controller
``kubectl.exe port-forward -n ingress-nginx ${ingress-controller pod name} 8080:80``

## 2.generte ssl key & ssl cert
``
 openssl req -x509 -newkey rsa:4096 -nodes -keyout tls.key -out tls.crt -days 90
``
## 3.create secret tls
``
  kubectl  create secret tls demo-localdev-https-secret --key tls.key --crt tls.crt
``
## 4.create ingress with tls
``
  kubectl create ingress platform-https --class=nginx --rule=demo.localdev.me/*=platform:80,tls=demo-localdev-https-secret
``

