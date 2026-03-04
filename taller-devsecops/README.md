#  Qué es DevSecOps


DevSecOps significa Development (Desarrollo) + Security (Seguridad) + Operations (Operaciones).

Es una metodología que integra la seguridad dentro de todo el proceso de desarrollo de software, en lugar de dejarla solo al final.


## Objetivo principal

Detectar y corregir vulnerabilidades lo más temprano posible, reduciendo riesgos, costos y tiempo.

DevSecOps aplica seguridad en cada etapa:

1.  Planificación
  - Identificar riesgos.
  - Definir requisitos de seguridad.
2.  Desarrollo
  - Código seguro.
  - Revisión de código.
3.  Integración continua (CI/CD)
  - Escaneo automático de vulnerabilidades.
  - Pruebas de seguridad automatizadas.
4.  Despliegue
  - Configuración segura.
  - Control de acceso.
5.  Monitoreo
  - Logs y alertas.
  - Detección de ataques.

# Preguntas Orientadoras (Análisis DevSecOps)

### Trazabilidad: ¿Por qué es un riesgo de seguridad dejar la configuración de user.name y user.email vacía o utilizar datos genéricos en un entorno empresarial?

En un entorno empresarial, cada cambio en el código debe poder rastrearse hasta la persona que lo realizó. Si user.name y user.email están vacíos o se usan datos genéricos, se pierde la trazabilidad de los commits.Esto representa un riesgo de seguridad porque no se puede identificar quién introdujo un cambio, una vulnerabilidad o un error en el sistema. Además, dificulta auditorías de seguridad, investigaciones de incidentes y el control de responsabilidades dentro del equipo


### Cifrado Asimétrico: En el caso de usar SSH, ¿cuál es la diferencia funcional entre la llave privada y la pública? ¿Qué pasaría si un tercero obtiene acceso a tu llave privada?

En la autenticación SSH se utiliza criptografía asimétrica que funciona con dos llaves:

  - Llave pública: se comparte con el servidor (por ejemplo, GitHub) y sirve para identificar al usuario.
  - Llave privada: se mantiene segura en el equipo del usuario y se utiliza para firmar la autenticación.
    
Si un tercero obtiene acceso a la llave privada, podría autenticarse como si fuera el usuario legítimo. Esto le permitiría acceder a repositorios, realizar cambios, subir código malicioso o robar información sensible. Por esta razón, la llave privada nunca debe compartirse ni almacenarse en lugares públicos.

### Principio de Mínimo Privilegio: Si decides usar un Token de Acceso Personal (PAT), ¿qué riesgos conlleva asignarle permisos de "Administrador" (Full Control) en lugar de solo permisos de "Lectura/Escritura"?

El principio de mínimo privilegio establece que un sistema o usuario debe tener solo los permisos necesarios para realizar su tarea. Si un PAT tiene permisos de administrador (Full Control), el token podría realizar acciones críticas como eliminar repositorios, modificar configuraciones, gestionar colaboradores o acceder a información sensible.Si el token tiene únicamente permisos de lectura o escritura, el impacto de una posible filtración sería mucho menor.


### Higiene del Repositorio: ¿Para qué sirve el archivo .gitignore desde una perspectiva de seguridad? (Menciona al menos dos tipos de archivos que nunca deberían subirse al repositorio remoto).

El archivo .gitignore permite definir qué archivos o carpetas no deben incluirse en el repositorio. Desde una perspectiva de seguridad, ayuda a evitar que información sensible o innecesaria sea subida a un repositorio remoto.

### Exposición de Secretos: Si accidentalmente subes una llave de API o una contraseña al repositorio en GitHub, ¿es suficiente con borrarla y hacer un nuevo commit? Justifica tu respuesta.

No, no es suficiente. Aunque el archivo se elimine en un nuevo commit, la información sensible seguirá existiendo en el historial del repositorio. Cualquier persona con acceso al repositorio podría revisar los commits anteriores y recuperar la clave expuesta.
Revocar inmediatamente la clave o contraseña comprometida.

1. Generar una nueva credencial segura.
2. Eliminar el secreto del historial del repositorio utilizando herramientas de reescritura de historial (como git filter-repo o git rebase).
3. Aplicar buenas prácticas para evitar que vuelva a ocurrir, como usar variables de entorno o gestores de secretos.
