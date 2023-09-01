## Create namespace

    - kubectl create namespace

<img width="412" alt="image" src="https://github.com/ManishNegi963/kubernetes_cluster_with_nginx_running/assets/124788172/96f85e64-9420-41e4-848c-e3a3dbfb6dfc">


## View namespace

    - kubectl get namespace

<img width="401" alt="image" src="https://github.com/ManishNegi963/kubernetes_cluster_with_nginx_running/assets/124788172/264cfb0b-c839-4064-96b8-132da827beac">


## Create pod.yaml

      - vim pod.yaml

  <img width="380" alt="image" src="https://github.com/ManishNegi963/kubernetes_cluster_with_nginx_running/assets/124788172/cff9f6e1-aec0-42d1-a0cc-56c5188e8e37">


      - cat pod.yaml



<img width="307" alt="image" src="https://github.com/ManishNegi963/kubernetes_cluster_with_nginx_running/assets/124788172/2c5c485f-ab9f-423f-b7af-9326bc127f96">



## Apply pod.yaml

    - kubectl apply -f pod.yaml

<img width="385" alt="image" src="https://github.com/ManishNegi963/kubernetes_cluster_with_nginx_running/assets/124788172/3279f0dc-ab35-45df-9581-2debf5ca7859">


## View pods

    - kubectl get pods

    - kubectl get pods -n nginx-ns

<img width="435" alt="image" src="https://github.com/ManishNegi963/kubernetes_cluster_with_nginx_running/assets/124788172/802c4100-4591-4ae5-90f1-373e97ffca7a">


## Create deployment.yaml

    - vim deployment.yaml

  <img width="392" alt="image" src="https://github.com/ManishNegi963/kubernetes_cluster_with_nginx_running/assets/124788172/d2171ea7-4e23-4591-9d87-0f5708ee541d">

    
    - cat deployment.yaml


 <img width="443" alt="image" src="https://github.com/ManishNegi963/kubernetes_cluster_with_nginx_running/assets/124788172/aec13004-2955-46e3-a5f9-374f698644dd">
 

## Apply deployment.yaml

    - kubectl apply -f deployment.yaml

<img width="427" alt="image" src="https://github.com/ManishNegi963/kubernetes_cluster_with_nginx_running/assets/124788172/890af4f4-1218-4a47-bc2d-c04a4a9894d3">

## View pods

    - kubectl get pods -n nginx-ns

<img width="482" alt="image" src="https://github.com/ManishNegi963/kubernetes_cluster_with_nginx_running/assets/124788172/9a1862b3-e9c8-44a0-b8da-1c4d440d91ec">

## Edit deployment to change replicas to 5

    - vim deployment.yaml
    
    - cat deployment.yaml

  <img width="494" alt="image" src="https://github.com/ManishNegi963/kubernetes_cluster_with_nginx_running/assets/124788172/676ea3de-e11f-421e-90a5-b34cf5d472bd">

## Apply edited deployment (pods will be auto-scaled to get the desired state mentioned in the deployment file)

    - kubectl apply -f deployment.yaml

<img width="478" alt="image" src="https://github.com/ManishNegi963/kubernetes_cluster_with_nginx_running/assets/124788172/a3581d98-2579-4699-b1b9-3679a12e24d7">

## View pods

    - kubectl get pods -n nginx-ns

<img width="511" alt="image" src="https://github.com/ManishNegi963/kubernetes_cluster_with_nginx_running/assets/124788172/867b0fd5-4039-4091-bcff-5989087c2ce2">


## View the IP address of the pods

    - kubectl get pods -n nginx-ns -o wide

<img width="850" alt="image" src="https://github.com/ManishNegi963/kubernetes_cluster_with_nginx_running/assets/124788172/7f680f12-94bf-45c9-9ede-9c195d8a1d27">


## View running deployment

    - kubectl get deployment -n nginx-ns

   <img width="426" alt="image" src="https://github.com/ManishNegi963/kubernetes_cluster_with_nginx_running/assets/124788172/f9fcd76c-1b57-4a6d-b0e9-5e16c681e867">


## View more information about the deployment

    - kubectl describe deployment nginx-deployment -n nginx-ns

<img width="597" alt="image" src="https://github.com/ManishNegi963/kubernetes_cluster_with_nginx_running/assets/124788172/ffdd817d-6975-4054-a6d4-7638fbf1bc8a">


  ## Scaling deployment with scale command

    - kubectl scale deployment nginx-deployment --replicas=4 -n nginx-ns

  <img width="645" alt="image" src="https://github.com/ManishNegi963/kubernetes_cluster_with_nginx_running/assets/124788172/88477055-c11f-46ad-8914-277352dd3fd7">

## View pods after scaling command

    - kubectl get pods -n nginx-ns

  <img width="546" alt="image" src="https://github.com/ManishNegi963/kubernetes_cluster_with_nginx_running/assets/124788172/d498b188-8b87-47e1-9be4-465e8171af83">

## Create and apply service.yaml

    - vim service.yaml
    
    - cat service.yaml
    
    - kubectl apply -f service.yaml 

  <img width="421" alt="image" src="https://github.com/ManishNegi963/kubernetes_cluster_with_nginx_running/assets/124788172/c1c8a8e4-0142-4cfa-85c3-1dd7804c311a">

## View service

    - kubectl get service -n nginx-ns

  <img width="541" alt="image" src="https://github.com/ManishNegi963/kubernetes_cluster_with_nginx_running/assets/124788172/084f3bb8-8a79-4f2b-b1e1-496662f8af73">


## Enable port on security group

<img width="1019" alt="image" src="https://github.com/ManishNegi963/kubernetes_cluster_with_nginx_running/assets/124788172/8585ee2f-6b0d-4c83-9b8e-e349105e7951">


## Nginx working 

<img width="841" alt="image" src="https://github.com/ManishNegi963/kubernetes_cluster_with_nginx_running/assets/124788172/82a96bb1-d2e0-4123-a1c4-7a7468db551f">


## Delete pod

    - kubectl get pods -n nginx-ns

<img width="564" alt="image" src="https://github.com/ManishNegi963/kubernetes_cluster_with_nginx_running/assets/124788172/bf211a56-af75-4465-a2a7-caf1badce191">

    kubectl delete pod nginx-deployment-747d4bbf58-25v8z -n nginx-ns

<img width="670" alt="image" src="https://github.com/ManishNegi963/kubernetes_cluster_with_nginx_running/assets/124788172/a0921456-916a-4e1e-9cc9-52ed474048fa">


## Auto healed pod that is deleted

    kubectl get pods -n nginx-ns

<img width="501" alt="image" src="https://github.com/ManishNegi963/kubernetes_cluster_with_nginx_running/assets/124788172/41ea9d36-2c5e-4597-ab23-db4d451cdedb">

## Application still running even when the pod is deleted as it is auto healing.

<img width="842" alt="image" src="https://github.com/ManishNegi963/kubernetes_cluster_with_nginx_running/assets/124788172/6e1387bd-f127-4b7a-b883-9c11e4899088">

