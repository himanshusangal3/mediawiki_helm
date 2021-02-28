# Helm Chart Deployment of MediaWiki with Mariadb

####Prerequisite
```
Working Kubernetes cluster
Helm 3 should be installed
```

###Clone this repositry from below URL

```
git clone https://github.com/himanshusangal3/mediawiki_helm.git
```
###Ran below command to install helm bundle at the same path where you have clone it.
```
helm install mediawiki ./mediawiki_helm
```

### Verify the helm deploy ment using
```
helm ls
```
Output should be like

```
NAME            NAMESPACE       REVISION        UPDATED                                 STATUS          CHART               APP VERSION
mediawiki       default         1               2021-02-28 10:42:21.388349835 +0000 UTC deployed        mediawiki-0.1.0     1.0

```

###Verify pods and services
```
kubectl get pods
```
#Output should be like
```
root@ip-172-31-70-143:~# kubectl get pods
NAME                             READY   STATUS    RESTARTS   AGE
mediawiki-app-855ffbf6df-tbpp6   1/1     Running   0          11m
mediawiki-db-6846cd895f-mzr4d    1/1     Running   0          11m
root@ip-172-31-70-143:~#

```

Check services

```
kubectl get svc
```

#Output should be like

```
root@ip-172-31-70-143:~# kubectl get svc
NAME            TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)          AGE
kubernetes      ClusterIP   10.96.0.1        <none>        443/TCP          8h
mediawiki-app   NodePort    10.107.141.188   <none>        8080:30115/TCP   12m
mediawiki-db    ClusterIP   10.103.95.2      <none>        3306/TCP         12m
root@ip-172-31-70-143:~#

```

###Now All the pods are open

#Open the url using node name http://<node_name>:30115

Click on the ```Please set up the wiki first.```

###Click on Continue Button.
### Again Click on Continue Button.

###Now Connect to DB page open

In the <b> Database host:</b>
Please enter <b> mediawiki-db </b>

In the <b> Database username:</b>
Please enter <b> wikiuser </b>

In the <b> Database password:</b>
Please enter <b> example </b>

###Then Click on Continue Button.

###Do Further configuration.
