# Bienvenido a Nexopus Docs

Bienvenido al **Manual de Usuario de Nexopus**, la plataforma de automatización de casos y procesos integrada con **Ivanti, Dialvox y sistemas corporativos de Open Group**.

Aquí encontrarás guías detalladas para:
 - Navegar y usar la aplicación web.
 - Configurar tu perfil y tus accesos.
 - Comprender los módulos disponibles.
 - Administrar usuarios y roles.
 - Resolver incidencias comunes.

---

## 🧭 Estructura del Manual

1. **Inicio:** Esta sección se presenta una descripción general de proyecto, su objetivo general y sistema integrados.   
2. **Uso general:** Esta sección presenta los conceptos básicos para inicio de sesión y navegación sobre la plataforma.  
2. **Módulos:** Esta sección explicación de cada área funcional de la plataforma.  
3. **Administración:** Esta sección presenta la gestión de usuarios, parámetros del sistema y flujo funcional.  
4. **Soporte:** Aquí se presenta, preguntas frecuentes y tips para enfrentar posibles fallas, además de la forma de interactuar con el equipo técnico de soporte.

---

## **Descripción**

Este proyecto implementa una solución integral para la creación automática y enriquecida de casos en el ITSM Ivanti. A través de la sinergia entre la inteligencia artificial de gestión de llamadas de Dialvox y las capacidades de procesamiento e inteligencia artificial de nuestra plataforma Nexopus, transformando las interacciones de voz de los usuarios clientes en tickets de servicio completos.

## **Objetivo General**

Automatizar el proceso de creación de tickets en la plataforma Ivanti a partir de las llamadas recibidas por el asistente de llamadas del sistema Dialvoxen al  Centro de Servicios (CdS) , asegurando la máxima calidad y completitud de la información registrada.

## **Descripción funcional de la Arquitectura y Flujo de Trabajo**

![Diagarama funcional de integración](./assets/diagrama_solucion_entidades-flujo.png)

El proyecto se basa en la integración de tres componentes principales:

1. **Dialvox/Oriana (Sistema de Recepción de Llamadas con IA):**

    - Actúa como el primer punto de contacto para el usuario.
    - Utiliza un sistema de respuesta de voz interactiva (IVR) inteligente para comprender la intención inicial del usuario.
    - Graba la conversación para su posterior análisis.

2. **Nexopus (Plataforma de Orquestación e Inteligencia Artificial):**

    - Recibe la grabación y/o la transcripción de la llamada desde Dialvox.
    - Aplica algoritmos de Procesamiento del Lenguaje Natural (PLN) para analizar el contenido de la conversación.
    - Su motor de IA se encarga de la extracción de entidades: Identifica y extrae información clave como nombre del solicitante, número de identificación, descripción del problema, activos involucrados, etc.
    - Clasificación y Categorización: Por medio de su IA documenta los indicentes y requerimientos con un Servicio,  Categoría y Subcategoría.

* **Ivanti (Sistema de Gestión de Tickets - ITSM):**
A través de su API, recibe la información estructurada desde Nexopus.
    - Se crea un nuevo caso de manera automática en la cola correspondiente del Centro de Servicios.
    El caso incluye:
    Título descriptivo.
    Datos del solicitante.
    Descripción detallada del problema (extraída de la conversación).
    Categorización sugeridos por la IA.
    

Resultado:

La implementación de este proyecto permite la documnetación automática de tickets que son atendidos en llamada a un centro de Servivicio con una intervención manual mínima o nula. Esto permitirá a los gestores del CdS recibir casos mejor documentados, lo que a su vez acelerará el tiempo de diagnóstico y resolución.

