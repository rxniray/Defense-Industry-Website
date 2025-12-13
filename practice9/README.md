# Лабораторна робота №9

### Діаграма Kubernetes-додатку

![Kubernetes-app](./practice9/kyberneres_diagram.png)

На даній діаграмі моделюється схема Flask-додатку prod.nexus. 

В кластері він живе під namespace`ом demo.

Трафік до кластера заходить через домен api.prod.nexus.ua, далі потрапряє до Load Balancer`a, тоді через Ingress потрапляє до ClusterIP, після чого потрапляє в Deployment і в Pod'и. Три pod'и було обрано для більшої відмовостійкості та взаємозаміності. 

При push до origin проєкт потрапляє до CI\CD(GitHub Actions), після чого контейнер збирається та потрапляє до Container Registry(GitHub Container Registry). Після deployment'у контейнери з registry витягуються до pod'ів.



