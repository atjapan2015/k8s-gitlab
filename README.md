#mkdir -p /u02/k8sdata/gitlabpath/gitlabpgpath
#mkdir -p /u02/k8sdata/gitlabpath/redispath
#mkdir -p /u01/k8sdata/gitlabpath/gitlabpgpath
#sudo chmod 777 /u02/k8sdata/gitlabpath/redispath
#sudo chmod 777 /u02/k8sdata/gitlabpath/gitlabpgpath
#sudo chmod 777 /u02/k8sdata/gitlabpath/gitlabpgpath

#k apply -f gitlab-pg-pv.yaml
k apply -f gitlab-pvc.yaml
#k apply -f gitlab-pv.yaml
k apply -f gitlab-rc.yaml
k apply -f gitlab-svc-lb.yaml
k apply -f gitlab-svc.yaml
k apply -f postgresql-rc.yaml
k apply -f postgresql-svc.yaml
#k apply -f redis-pv.yaml
k apply -f redis-rc.yaml
k apply -f redis-svc.yaml

root/gitlab123
