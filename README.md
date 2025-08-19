correcion de errores

el proyecto fue creado en gradle-groovy, por lo cual se creo un nuevo proyecto en sprinboot verificando que el proyecto se cree en maven

Curso
1- linea 8 faltan las anotaciones @Entity  y @Table(name="curso") las cuales se ponen antes de la linea 8.
2- linea 10 solo se encuentra escrito @I el el cual se encuentra incompleto por que es @Id.
3- linea 11 solo se encuentra escrito @Ge(Strategy=IDENTY) el cual se encuetra incompleto y mal escrito se debe verificar que este bien escrito @GeneratedValue(strategy = GenerationType.IDENTITY) se puede evitar el error revisando que si se autocompleten las palabras ingresadas
4- linea 14 falta la anotacion @Column la cual se necesita para las columnas de la base de datos.
5- linea 15 falta el punto y coma al final siempre se debe verificar ya que es un error muy comun
6- linea 18 tiene un punto y coma que no se utiliza para las anotaciones
7- linea 20 falta el punto y coma al final y el private para el Docente docente
8- linea 30 en adelante falta generar el getter and setter el cual siempre debe ir en el codigo siempre se debe tener en cuenta.

Usuario
1- linea 8 faltan las anotaciones @Entity  y @Table(name="curso") las cuales se ponen antes de la linea 8.
2- linea 11 falta el IDENTITY en la anotacion @GeneratedValue(strategy = GenerationType.IDENTITY) el cual se anexo
3- linea 12 la anotacion @Column no es necesaria ya que se estructuran es un Id.
4- linea 14 falta en la notacion @Column dentro de los parentesis:el nombre de la columna name="nombre" y  unique = false que significa que el nombre no es unico.
5- linea 17 la anotacion @Column esta mal escrita le faltaba la m antes de la n  y dentreo de los parentesis falta nullable = false y el length=80 para saber la cantidad de letras que se puede utilizar.
6- linea 20 falta la anotacion @Column para definirla dentro de la BD.
7- linea 23 tambien falta la anotacion @Column.
8- linea 28 tambien se le debe agregar la anotacion @Column y crear un enum para el TipoUsusario con el mismo nombre en una carpeta creada en java con el nombre ayudas y escribir los tipos de usuarios que se van a necesitar y luego volver a la linea 28 de usuario borrar y volver a escribir para importar los cambios.
9- linea 48 en adelante falta generar el getter and setter el cual siempre debe ir en el codigo siempre se debe tener en cuenta.

Docente

1- linea 9 faltan las anotaciones @Entity  y @Table(name="curso") las cuales se ponen antes de la linea 9.
2- linea 13 falta la anotacion @Id siempre es necesaria cuando se trabaja con ID
3- linea 16 falta la anotacion @Column (name = "especialidad", nullable = false, unique = false) con todos estos identifcadores de la anotacion.
4- linea 23 la linea tiene un escrito de mas el cual solo es id dentre de esta parte del codigo referencedColumnName = "id" que esta dentro de los parentsis.
5- se anexo el constructor vacio en la linea 27 y también el constructor completo con el getter y setter.


# 📚 Plataforma Educativa - Proyecto Spring Boot con Maven

Este proyecto es una plataforma educativa construida con Spring Boot y Maven. Su objetivo principal es gestionar entidades como `Curso`, `Usuario` y `Docente`, integrando autenticación, relaciones entre entidades y persistencia en base de datos. Inicialmente creado en Gradle-Groovy, se migró a Maven para facilitar la integración con herramientas y dependencias más comunes en entornos empresariales.

---

## ✅ Errores Corregidos

### 🔧 Entidad `Curso`
1. **Faltaban anotaciones `@Entity` y `@Table`**  
   Se agregaron antes de la declaración de clase para mapear correctamente la entidad a la tabla `curso`.

2. **Anotación incompleta `@I` → `@Id`**  
   Se corrigió para identificar el campo como clave primaria.

3. **Error en `@Ge(Strategy=IDENTY)`**  
   Corregido a `@GeneratedValue(strategy = GenerationType.IDENTITY)` para autogenerar el ID.

4. **Falta de `@Column` en atributos**  
   Se agregó para mapear correctamente los campos a columnas de la base de datos.

5. **Falta de punto y coma en línea 15**  
   Se añadió para evitar errores de compilación.

6. **Uso incorrecto de punto y coma en anotaciones**  
   Eliminado para mantener sintaxis válida.

7. **Falta de `private` y punto y coma en atributo `Docente docente`**  
   Corregido para cumplir con las reglas de encapsulamiento.

8. **Falta de getters y setters**  
   Se generaron para todos los atributos, asegurando acceso controlado.

---

### 🔧 Entidad `Usuario`
1. **Faltaban anotaciones `@Entity` y `@Table(name="usuario")`**  
   Añadidas para mapear correctamente la clase.

2. **Falta de `IDENTITY` en `@GeneratedValue`**  
   Corregido para asegurar generación automática del ID.

3. **Uso innecesario de `@Column` en campo `id`**  
   Eliminado, ya que `@Id` y `@GeneratedValue` son suficientes.

4. **Falta de propiedades en `@Column` para `nombre`**  
   Añadido `name="nombre", unique=false`.

5. **Error de escritura en `@Column` para `apellido`**  
   Corregido y se añadieron propiedades `nullable=false, length=80`.

6–8. **Falta de `@Column` en varios atributos**  
   Añadidas en `correo`, `contraseña`, y `tipoUsuario`.

9. **Falta de enum `TipoUsuario`**  
   Se creó en carpeta `ayudas` y se integró correctamente.

10. **Falta de getters y setters**  
    Generados para todos los atributos.

---

### 🔧 Entidad `Docente`
1. **Faltaban anotaciones `@Entity` y `@Table(name="docente")`**  
   Añadidas para mapear correctamente la clase.

2. **Falta de `@Id` en campo `id`**  
   Añadido para definir clave primaria.

3. **Falta de `@Column` en campo `especialidad`**  
   Añadido con propiedades `name="especialidad", nullable=false, unique=false`.

4. **Error en `referencedColumnName = "id"`**  
   Se corrigió la sintaxis para evitar ambigüedad.

5. **Constructores vacíos y completos**  
   Añadidos junto con getters y setters para facilitar la creación de objetos.

---

## 🛠️ Conexión a la Base de Datos (Paso a Paso)

1. **Configura el archivo `application.properties` o `application.yml`:**

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/educacion_db
spring.datasource.username=tu_usuario
spring.datasource.password=tu_contraseña
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL8Dialect

2- Verifica que MySQL esté corriendo y que la base de datos educacion_db exista.
3- Agrega la dependencia de MySQL en pom.xml:

<dependency>
  <groupId>mysql</groupId>
  <artifactId>mysql-connector-java</artifactId>
  <scope>runtime</scope>
</dependency>

5- Ejecuta el proyecto con Spring Boot.
Las tablas se crearán automáticamente si las entidades están correctamente anotadas.

🧠 Recomendaciones para Evitar Errores- ✅ Usa autocompletado en tu IDE (como VS Code o IntelliJ) para evitar errores de escritura.
- ✅ Revisa siempre que las anotaciones estén completas y bien ubicadas.
- ✅ Genera getters, setters y constructores desde el IDE para evitar omisiones.
- ✅ Verifica que cada atributo tenga su correspondiente anotación @Column si se requiere persistencia.
- ✅ Mantén una estructura clara en tu proyecto: carpetas separadas para entidades, repositorios, servicios y controladores.
- ✅ Documenta cada clase con comentarios breves sobre su propósito.
- ✅ Usa validadores como @NotNull, @Size, etc., para mejorar la integridad de los datos.









