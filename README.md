# Diagrama y código
Elabora un documento en markdown que incluya lo siguiente:

1) Breve descripción del proceso realizado.

2) Código fuente del diagrama anotado en sus etiquetas.

3) Código java de las clases.

## Breve descripción del proceso realizado
Tras la lectura de las caracteristicas a implementar y la consideración de los diversos tipos de relaciones a tratar, añadir, recubrir y unir las diferentes tablas, asegurándose de usar las conexiones correctas para reflejar dichas relaciones.

A la hora de recubrir, dividir los atributos de las operaciones a su vez que se indican los tipos de datos en estos primeros. La visibilidad se marcará en ambos.

Posteriormente, incorporar las cordinaliades necesarias en el esquema.

## Diagrama
```mermaid
classDiagram
    Conferencia "1" --* "1..*"	Sesion : Tiene
    Sesion "1" -- "N" Participante : Acoje
    Participante <|--  Orador : Es
    Participante <|--  Publico : ES

    Sesion "1..*" --> "1..*" Artigo_Cientifico : SePresenta
    Artigo_Cientifico <|-- Corto
    Artigo_Cientifico <|-- Largo
    
    Orador "0..1" <-- "0..1" Autor : Es
    Autor "1..*" -- "1..*" Artigo_Cientifico : Escribe

    class Conferencia{
        + String Nombre
        + String Tipo
        + String Direccion 
    }

    class Artigo_Cientifico{
        + String Nombre
        + String Tema
        + String Afiliacion
        + Date Fecha_Publicacion
        + String Conclusion
    }

    class Sesion{
      + String Nombre
      + Date Fecha_de_inicio
      + Date Fecha_de_fin
    }

    class Participante{
      + String Nombre
      + String Apellido1
      + String Apellido2
          
      - cancel()
      - inscribe()
      - confirmInscription()
    }

    class Publico {
        + String Tipo_Entrada
    }

    class Orador {
        + String Sala
    }

    class Autor {
        + String Titulos
        + String Premios
    }

    class Corto {
        + Int Num_palabras
    }

    class Largo {
        + String Resumen
        + Int Num_Paginas
    }
```

## Código java de las clases
```java
import java.util.Date;

public abstract class Conferencia {
    public String nombre;
    public String tipo;
    public String direccion;
    public Conferencia(String nombre, String tipo, String direccion) {
        this.nombre = nombre;
        this.tipo = tipo;
        this.direccion = direccion;
    }
    public String getNombre() {
        return nombre;
    }
    public void setNombre(String nombre) {
        this.nombre = nombre;
    }
    public String getTipo(){
        return tipo;
    }
    public void setTipo(String tipo){
        this.tipo = tipo;
    }
    public String getDireccion() {
        return direccion;
    }
    public void setDireccion(String direccion) {
        this.direccion = direccion;
    }
}

public class Sesion {
    public String nombre;
    public Date fecha_de_inicio;
    public Date fecha_de_fin;
    public Sesion(String nombre, Date fecha_de_inicio, Date fecha_de_fin) {
        this.nombre = nombre;
        this.fecha_de_inicio = fecha_de_inicio;
        this.fecha_de_fin = fecha_de_fin;
    }
    public String getNombre() {
        return nombre;
    }
    public void setNombre(String nombre) {
        this.nombre = nombre;
    }
    public Date getFecha_de_inicio(){
        return fecha_de_inicio;
    }
    public void setFecha_de_inicio(Date fecha_de_inicio){
        this.fecha_de_inicio = fecha_de_inicio;
    }
    public Date getFecha_de_fin(){
        return fecha_de_fin;
    }
    public void setFecha_de_fin(Date fecha_de_fin){
        this.fecha_de_fin = fecha_de_fin;
    }
}

public class Participante {
    public String nombre;
    public String Apellido1;
    public String Apellido2;
    private

// SEGUIR!!!


}

public class Artigo_Cientifico {
    String nombre;
    String tema;
    String afiliacion;
    Date fecha_Publicacion;
    String conclusion;
    public Artigo_Cientifico(String nombre, String tema, String afiliacion, Date fecha_Publicacion, String conclusion) {
        this.nombre = nombre;
        this.tema = tema;
        this.afiliacion = afiliacion;
        this.fecha_Publicacion = fecha_Publicacion;
        this.conclusion = conclusion;
    }
    public String getNombre() {
        return nombre;
    }
    public void setNombre(String nombre) {
        this.nombre = nombre;
    }
    public String getTema() {
        return tema;
    }
    public void setTema(String tema) {
        this.tema = this.tema;
    }
    public String getAfiliacion(){
        return afiliacion;
    }
    public void setAfiliacion(String afiliacion){
        this.afiliacion = afiliacion;
    }
    public Date getFecha_Publicacion(){
        return fecha_Publicacion;
    }
    public void setFecha_Publicacion(Date fecha_Publicacion){
        this.fecha_Publicacion = fecha_Publicacion;
    }
    public String getConclusion(){
        return conclusion;
    }
    public void setConclusion(){
        this.conclusion = conclusion;
    }
}
```#   e x C D _ U M L  
 