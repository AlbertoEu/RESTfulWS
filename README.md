# RESTfulWS

Acerca de:
Computación Avanzada en Java - Evidencia Final

Evidencia que es un compendio de todo lo realizado en el curso como desarrollo web con Java, instalación y configuración de contenedores de aplicaciones web, uso del framework Spring MVC.
En donde realizamos un git para el desarrollo de esta evidencia que incluye cuatro recursos REST en Spring, diseño Model-View-Controller y Repository, en donde su función es la de enumerar archivos de un directorio, descargar, subir y borrar archivos, así como enviar notificaciones por eventos.

Proyecto:
Como se mencionó anteriormente, este proyecto tiene la función de un CRUD de archivos, así como poder enviar notificaciones.

Esta evidencia se realizó en base a la actividad 13. que es la base de la práctica del tema 12 (v.1.12.2).
En donde esta incluía ya los siguientes paquetes:
component
config
filter
form
model
repository
rest
service
view
web

En donde se incluyeron las siguientes clases:

FileRest.java
  Que utiliza:
  FileService.java
  FileServiceImpl.java
  Y tiene los siguientes atributos y métodos:
  fileService : FileService
  showOptions() : ResponseEntity<?>
  downloadFile(String) : View
  deleteFile(String) : String
  uploadFile(MultipartFile, String, String) : ResponseEntity<?>
  
DirectoryRest.java
  Que utiliza:
  File.java
    serialVersionUID : long
    name : String
    path : String
    fullPath : String
    sizeBytes : long
    _link : Link
  Link.java
    href : String
    rel : String
  FileLinkListResource.java
    links : List<Link>
    files: List<File>
  FileService.java
  FileServiceImpl.java
  Y tiene los siguientes atributos y métodos:
  fileService : FileService
  showOptions() : ResponseEntity<?>
  getFilesJSON(String) : Map<String, Object>
  getFilesXML(String) : FileLinkListResource
  
  
NotificationRest.java
  Que utiliza:
  FileService.java
  FileServiceImpl.java
  Notificaction.java
    serialVersionUID : long
    subject : String
    message : String
    toAddress : List<String>
    ccAddress : List<String>
    messageId : String
    status : String
    Notification() - constructor
    Notification(String, String, List<String>, List<String>) - constructor
    Notification(String, String, List<String>) - constructor
    getSubject() : String
    setSubject(String) : void
    getMessage() : String
    setMessage(String) : void
    getToAddress() : List<String>
    setToAddress(List<String>) : void
    getCcAddress() : List<String>
    setCcAddress(List<String>) : void
    toString() : String
    getMessageId() : String
    setMessageId(String) : void
    getStatus() : String
    setStatus(String) : void
  NotificationRepositoryImpl.java
    notificationDB : Map<String, Notification>
    getNotifications() : List<Notification>
    getNotification(String) : Notification
    createNotification(String, String, String, List<String>, List<String>) : Notification
    updateNotification(String, Notification) : Notification
    addNotification(Notification) : void
  NotificationLinkListResource.java
    links : List<Link>
    notifications : List<Notification>
    getLinks() : List<Link>
    setLinks(List<Link>) : void
    addLink(Link) : void
    getNotifications() : List<Notification>
    setNotifications(List<Notification>) : void
  NotifcationServiceImpl.java
    mailSender : MailSender
    notificationRepository : NotificationRepository
  logger : Logger
  notify(String, String, List<String>, List<String>) : Notification
  getNotifications() : List<Notification>
  Y tiene los siguientes atributos y métodos:
  logger : Logger
  notificationService : NotificationService
  showOptions() : ResponseEntity<?>
  getNotificationsJSON() : Map<String, Object>
  getNotificationsXML() : NotificactionLinkListResource
  notify(String, String, String, String) : ResponseEntity<?>
  
UserRest.java
  Que utiliza:
  UserService.java
  UserServiceImpl.java
  IndexRest.java
    showOptions() : ResponseEntity<?>
    indexJson() : Map<String, Object>
    indexXml() : Resource
  Y tiene los siguientes atributos y métodos:
  userService : UserSErvice
  getUsersJSON() : Map<String, Object>
  getUsersXML() : UserLinkListResource
  getUserJSON(String) : Map<String, Object>
  getUserXML(String) : UserResource
  deleteUser(String : void
  create(UserForm) : ResponseEntity<Void>
  update(String, UserForm) : void
  userIndex() : ResponseEntity<Void>
  userOptions(String) : ResponseEntity<Void>
  
Librerías:
JavaSE-1.8
Dependencias de Maven

Webcontainer:
Se recomienda usar Tomcat

Guías:
  
a) Instalación
 1.- Clonar repositorio
 2.- Abrir projecto en un IDE
 3.- Exportar proyecto como WAR
 4.- Montar WAR en Webcontainer
 5.- Hacer deploy de este
 
b) Uso  
  Se debe de acceder al puerto del localhost donde se haya ejecutado el web container (localhost:8080)
  Después se debe de acceder al vínculo de la evidencia (http://localhost:8080/CS13304/Login)
  Accediendo a la liga anterior, se debería de poder acceder al login de la aplicación, y eventualmente a todas las demás características

c) Créditos  
  Alberto Eugenio Reyes Camacho
  #2749484

d) Licencia 
  En este repositorio se cuenta con un archivo que contiene la licencia de la aplicación
