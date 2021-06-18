Fargate-Start

Amazon Elastic Container Service (Amazon ECS) es un servicio de administración de contenedores altamente escalable y rápido que facilita la tarea de ejecutar, detener y administrar sus contenedores. Puede alojar sus contenedores en una infraestructura sin servidor que administre Amazon ECS mediante el lanzamiento de sus servicios o tareas en AWS Fargate.

Para aprender a utilizar Fargate tendremos una seríe de paso a seguir 

Paso #1 
 Debemos de tener una imagen alojada en algun reposiorio en este ejemplo en particular yo utilizare una imagen que tengo alojada en Docker Hub
  
  ![image](https://user-images.githubusercontent.com/36380066/122507557-06d48f80-cfc6-11eb-907b-50dc6ae1b01a.png)

Paso #2
 Definir una tarea
 
 para esto debemos:
 
   ir a us-east-2.console.aws.amazon.com, y buscar el servició de Clusters
 
   ![image](https://user-images.githubusercontent.com/36380066/122509394-52d50380-cfc9-11eb-9d43-630781d9870b.png)

   ya que nos encontramos ahí nos vamos al apartado de Task Definitions 
        
   ![image](https://user-images.githubusercontent.com/36380066/122508678-fa513680-cfc7-11eb-86ba-59fc9a2038ee.png)

   Creamos una tarea de tipo Fargate
   
   ![image](https://user-images.githubusercontent.com/36380066/122509597-ae06f600-cfc9-11eb-8235-623b8bc69ebc.png)
    
   Llenamos los campos que son necesarios hasta la parte de añadir un contenedor 
   
   ![image](https://user-images.githubusercontent.com/36380066/122510202-cc212600-cfca-11eb-9da0-7a8904493568.png)
   
   Cuando llegamos a la parte de añadir un contenedor hay que tomar algunas cosas en cuenta para esto iré explicando cada uno de los 
   campos necesario
   
   ![image](https://user-images.githubusercontent.com/36380066/122510328-0b4f7700-cfcb-11eb-836f-b06f8770cdef.png)

   Tenemos el campo de container name e image
   
   ![image](https://user-images.githubusercontent.com/36380066/122511439-d9d7ab00-cfcc-11eb-941c-d911a44fffb3.png)

   En el capo de image pondremos la url que nos proporciona Docker hub para poder acceder a la Imagen que tenemos 
   almacenada en nuestro repocitorio.
   
   ![image](https://user-images.githubusercontent.com/36380066/122511515-fe338780-cfcc-11eb-8986-cc7ec9869a46.png)

   Tenemos el campo de Memory Limits (MiB) el cual definimos límites de memoria rígidos y / o flexibles en MiB para su contenedor
   
   ![image](https://user-images.githubusercontent.com/36380066/122511593-1a372900-cfcd-11eb-8559-453d6b376e14.png)
   
   Paso #3
   
   Crear un Cluster

   ![image](https://user-images.githubusercontent.com/36380066/122512709-e2c97c00-cfce-11eb-9aa0-e9c447ae12c1.png)

   Para este tutorial elegiremos Networking only 
   
   ![image](https://user-images.githubusercontent.com/36380066/122512796-0ab8df80-cfcf-11eb-85ea-80e1e422e071.png)

   A continuación llenamos los campos que son necesarios
   
   Tenemos el campo de name en el cual pondremos el nombre que queremos que tenga nustro clouster además tenemos el
   campo Create VPC el cual habilitaremos, este campo nos ayudará para relacionar nuestra tarea y poderla correr.
   
   ![image](https://user-images.githubusercontent.com/36380066/122513174-a4808c80-cfcf-11eb-9147-495167626195.png)

   Y creamos el cluster
   
   ![image](https://user-images.githubusercontent.com/36380066/122514362-7c922880-cfd1-11eb-95c1-3b34323a8a9a.png)

   Paso #4 
   
   Corremos nuestra Tarea ya creada anteriormente

   Para esto nos vamos al apartadod de tareas y seleccionamos Run new Task
   
   ![image](https://user-images.githubusercontent.com/36380066/122514608-d1ce3a00-cfd1-11eb-8240-9a4b5891d50a.png)
   
   Y completamos todos los campos necesarios
   
   Seleccionamos Fargate
   
   ![image](https://user-images.githubusercontent.com/36380066/122514953-5751ea00-cfd2-11eb-9d1f-09febb367d4d.png)

   Algunos campos automaticamente los rellena aws
   
   ![image](https://user-images.githubusercontent.com/36380066/122515333-e959f280-cfd2-11eb-8b6d-cf64bdb99981.png)

   Seleccionamos el vpc que agregamos anteriormente 
   
   ![image](https://user-images.githubusercontent.com/36380066/122515850-a0566e00-cfd3-11eb-9728-895a77d2d2a0.png)

   Configuramos los grupos de seguridad para esta tarea, añadiendo los puertos en los cuales permitiremos trabajar 
   
   ![image](https://user-images.githubusercontent.com/36380066/122516179-0e029a00-cfd4-11eb-9e6d-a5f449dd7be0.png)

   Y corremos nuestra tarea
   
   ![image](https://user-images.githubusercontent.com/36380066/122516274-2ecaef80-cfd4-11eb-8bc6-1174f8691001.png)
   
   Solo esperamos a que el campo status cambie a running RUNNING
   
   ![image](https://user-images.githubusercontent.com/36380066/122516418-5f128e00-cfd4-11eb-8fc3-fcbdaf504d66.png)

   Felicidades ya tienes corriendo una tarea la cual contiene una imagen organizada con Fargate
   
   Solo para terminar, si deceas probar tu imagen solo copea la ip publica que te proporciona tu tarea y pegala en tu navegador para que la
   veas corriendo.
   
   ![image](https://user-images.githubusercontent.com/36380066/122516706-b6b0f980-cfd4-11eb-967d-f2d57658aedb.png)
   
   ![image](https://user-images.githubusercontent.com/36380066/122516750-c3cde880-cfd4-11eb-8647-6d30c532eb91.png)



   
   
   
