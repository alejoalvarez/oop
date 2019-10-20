[[_TOC_]]


## **¿Quién debe crear repositorios?**
- Movilizadores
- Equipo DevOps (para casos en los que no se tenga movilizador)

Los analistas mencionados anteriormente tienen los permisos necesarios para la creación de repositorios y deben velar por el cumplimiento de estándares en la creación de estos.

Cada equipo que requiera un repositorio debe solicitarlo a su movilizador.

## **Cómo se deben nombrar los repositorios?**

Se debe seguir el estándar de nombramiento definido. [Clic Aquí para ver Estándar](https://grupobancolombia.visualstudio.com/Vicepresidencia%20Servicios%20de%20Tecnolog%C3%ADa/_wiki/wikis/Vicepresidencia%20Servicios%20de%20Tecnolog%C3%ADa.wiki?wikiVersion=GBwikiMaster&pagePath=%2FDevOps%2FEst%C3%A1ndares%20DevOps%2FEst%C3%A1ndar%20nombramiento%20de%20Repositorios)

El analista debe saber el AW completo con el consecutivo incremental del componente y puede validarlo en USD para verificar que sea correcto.

_**Ejemplo**_. AW1172001

Se de saber el nombre del repositorio. Puede ser el nombre de la aplicación o del componente.

**_Ejemplos_**
- SVP
- MS_EntailmentOrchestrator
- TransferenciasInternacionalesSVP_UserProfile-query

El nombre del repositorio debe ser el AW, incluyendo el consecutivo incremental por componente, seguido de guion bajo y el nombre del repositorio.

**_Ejemplos:_** 
- AW0278001_SVP
- AW1170001_MS_EntailmentOrchestrator
- AW1100002_TransferenciasInternacionalesSVP_UserProfile-query

## **¿Cómo crear repositorios?**
Existen dos formas para crear un repositorio:

1.	Ingresar a project settings, buscar la opción repositorios como muestra la imagen y crear un nuevo repositorio.
![image.png](/.attachments/image-eefc279a-4468-4c86-a043-55405d20777a.png)

2.	Ingresando a la opción de Repos – files y en la parte superior donde se realiza la búsqueda de repositorios por nombre está la opción de **_+New repository_**

![image.png](/.attachments/image-f6797713-6876-4f56-b2ad-6d4912516b9d.png)

3. Ingresar el nombre del repositorio, el README y el .gitignore
![image.png](/.attachments/image-9df889c4-8ef7-40d3-a13d-77c8c18d9286.png)

**_NOTA:_** Siempre se debe agregar el .gitignore. 
Para los casos de angular VSTS no cuenta con un .gitignore. Se le debe especificar el desarrollador que él es el responsable de agregarlo al repositorio. 

## **Creación de Ramas**
Cuando se creen repositorios de aplicaciones se deben crear 3 ramas:

•	develop
•	release
•	master

Estando en el repositorio ingresar a la opción de branch

![image.png](/.attachments/image-ee354366-f9c1-4317-8189-455f0f33d141.png)

Y dar clic en **_New Branch_**
![image.png](/.attachments/image-9c59655d-e0c7-420f-915a-d27884998be6.png)

Escribir el nombre de la rama y dar clic en _Create branch_.
![image.png](/.attachments/image-79aa2f60-16ca-4a32-a784-049027604aa5.png)

## **Aplicar Políticas de Pull Request**

Se de aplicar políticas de Pull Request a las 3 ramas creadas (develop, release, master).

Posicionarse en la rama y dar clic en los puntos suspensivos (...)
![image.png](/.attachments/image-330910a9-22b6-4d3a-9621-2ab8999d9aba.png)

Configurar las siguientes políticas:
- Mínimo un aprobador
- Reiniciar la aprobación si hay nuevos cambios
- Work Items requeridos
- Cometarios resueltos
- Conservar el historial de commits cuando se realice el merge

![image.png](/.attachments/image-078ca137-2322-441f-babc-c05053b2739f.png)
![image.png](/.attachments/image-2b7482d5-e0b0-43f0-99ca-27ce37b1e585.png)

**_NOTA:_** Si ya se cuenta con pipeline de CI se debe agregar a la política de Build validation. 
En caso de no tenerlo, una vez este sea creado se debe agregar. 

Dando clic en **+Add build policy**, seleccionar el pipeline de CI y dar clic en SAVE

![image.png](/.attachments/image-20c264cc-1f45-43ed-a5d7-0640961524d7.png)

Finalmente se deben guardar las políticas
![image.png](/.attachments/image-e1b9365a-4b3c-4dd8-bbce-a438fa81f3be.png)

Una vez se hayan aplicado las políticas a las 3 ramas, estas deben quedar con el siguiente icono
![image.png](/.attachments/image-45705382-a2f4-4615-a057-f32d6063ad50.png)
