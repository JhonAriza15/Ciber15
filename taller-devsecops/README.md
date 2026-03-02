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

##  Trazabilidad: ¿Por qué es un riesgo de seguridad dejar la configuración de user.name y user.email vacía o utilizar datos genéricos en un entorno empresarial?

##  Cifrado Asimétrico: En el caso de usar SSH, ¿cuál es la diferencia funcional entre la llave privada y la pública? ¿Qué pasaría si un tercero obtiene acceso a tu llave privada?

##  Principio de Mínimo Privilegio: Si decides usar un Token de Acceso Personal (PAT), ¿qué riesgos conlleva asignarle permisos de "Administrador" (Full Control) en lugar de solo permisos de "Lectura/Escritura"?

##  Higiene del Repositorio: ¿Para qué sirve el archivo .gitignore desde una perspectiva de seguridad? (Menciona al menos dos tipos de archivos que nunca deberían subirse al repositorio remoto).

##  Exposición de Secretos: Si accidentalmente subes una llave de API o una contraseña al repositorio en GitHub, ¿es suficiente con borrarla y hacer un nuevo commit? Justifica tu respuesta.
