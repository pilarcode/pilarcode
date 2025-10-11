**Los tres pilares de la observabilidad: métricas, seguimientos y registros**

## **1. Introducción a la observabilidad**

Para comprender verdaderamente un sistema, debemos combinar información desde múltiples perspectivas y entender cómo se relacionan entre sí.  
Antes de analizar cualquier cosa, es necesario capturar aspectos del comportamiento del sistema. Esto se logra mediante **registros (logs)**, **métricas (metrics)** y **seguimientos (traces)**.

La **telemetría** es el proceso de recopilar y transmitir automáticamente datos desde sistemas remotos o distribuidos para supervisar, medir y rastrear su rendimiento o estado.  
Estos datos proporcionan información en tiempo real sobre el funcionamiento de las aplicaciones y son la base de la observabilidad moderna.

---

## **2. Los tres pilares de la observabilidad**

### **2.1 Registros (Logs)**

Un **registro** es una estructura de datos de solo anexión que documenta los eventos ocurridos en un sistema.  
Cada entrada contiene:

- Una **marca de tiempo** que indica cuándo ocurrió el evento.  
- Un **mensaje descriptivo** que detalla lo sucedido.  

Los registros son útiles para diagnósticos detallados, pero por sí solos carecen de contexto transaccional y dificultan correlacionar eventos entre servicios.

---

### **2.2 Métricas (Metrics)**

Las **métricas** ofrecen una visión general del estado actual del sistema.  
Son valores numéricos agregados, derivados de aplicar medidas estadísticas a grupos de eventos (por ejemplo, latencia promedio o número de solicitudes por segundo).  
Son esenciales para detectar anomalías, generar alertas y visualizar el estado del sistema a lo largo del tiempo.

---

### **2.3 Seguimientos (Traces)**

El **seguimiento distribuido** (popularizado por **Dapper** de Google) amplía el concepto de registro al añadir **contexto transaccional**.  
Un seguimiento permite reconstruir el recorrido completo de una solicitud a través de múltiples servicios, lo que facilita inferir causalidad y detectar cuellos de botella.

---

## **3. Telemetría y correlación de señales**

En la práctica, los registros, métricas y seguimientos comparten un ciclo de vida similar:  
todo comienza con la **instrumentación**, que captura y emite datos.

El análisis efectivo de telemetría implica correlacionar estas señales. Por ejemplo:

1. Una alerta en un panel de métricas indica una anomalía.  
2. Se buscan métricas relacionadas con comportamiento anómalo.  
3. Luego, se filtran eventos de registro que coincidan temporalmente.  
4. Finalmente, los seguimientos permiten reconstruir la cadena causal entre los eventos.  

Sin un mecanismo estandarizado (como identificadores de seguimiento o de intervalo), esta correlación resulta compleja en sistemas tradicionales.

---

## **4. OpenTelemetry (OTel)**
  
### **4.1 Qué es OpenTelemetry**

**OpenTelemetry (OTel)** es un proyecto de código abierto que proporciona herramientas y API estandarizadas para generar, recopilar y exportar datos de telemetría (trazas, métricas y registros).  
Sus principales objetivos son:

- **Telemetría unificada:** combinar seguimiento, registro y métricas bajo un mismo marco.  
- **Neutralidad del proveedor:** integración con múltiples backends (Prometheus, Datadog, New Relic, etc.).  
- **Multiplataforma:** soporte para varios lenguajes (Java, Python, Go, etc.).

---

### **4.2 Qué no es OpenTelemetry**

- No es una herramienta de monitorización ni un sistema de almacenamiento o visualización (para eso se usan Grafana, Jaeger o Prometheus).  
- No optimiza automáticamente el rendimiento de las aplicaciones.  
- Requiere configuración e integración con otras herramientas.

> En resumen, **OTel es un estándar de instrumentación y transporte de datos**, no una plataforma de observabilidad completa.

---

## **5. Especificación y componentes de OpenTelemetry**

### **5.1 Especificación de señal**

Define cómo se deben estructurar y recopilar los datos de telemetría (métricas, trazas y logs) de manera coherente entre distintos lenguajes y plataformas.

---

### **5.2 Instrumentación independiente del proveedor**

Permite instrumentar aplicaciones en diferentes lenguajes sin depender de un proveedor de observabilidad específico.  
Existen varios niveles:

- **Instrumentación automática:** no requiere cambios en el código.  
- **Bibliotecas de instrumentación:** extienden marcos que no tienen soporte nativo.  
- **Instrumentación manual:** modificación directa del código para mayor control.

---

### **5.3 El recopilador OpenTelemetry**

El **recopilador (Collector)** procesa la telemetría emitida por las aplicaciones:

- Recoge datos de diversas fuentes.  
- Los transforma, filtra, enriquece y normaliza.  
- Los enruta y reenvía a distintos backends.  

Esto proporciona flexibilidad y reduce la complejidad del procesamiento.

---

### **5.4 Protocolo OTLP (OpenTelemetry Protocol)**

El **OTLP** define cómo se codifican y transportan los datos de telemetría a través de la red.  
Es un **formato abierto, independiente del proveedor** y altamente interoperable.  
Soporta **HTTP/1.1, HTTP/2 y gRPC**, y se utiliza ampliamente en todo el ecosistema OTel.

Beneficios clave:

- Evita conversiones entre formatos.  
- Aumenta la consistencia de los datos.  
- Mejora la interoperabilidad entre herramientas.  

---

## **6. Instrumentación**

### **6.1 Concepto**

La **instrumentación** consiste en agregar código o usar herramientas para recopilar telemetría (registros, métricas y seguimientos) desde una aplicación.  
Es el primer paso hacia la observabilidad, permitiendo comprender el comportamiento del sistema en tiempo real.

---

### **6.2 Tipos de instrumentación**

| Tipo | Descripción | Ventajas | Desafíos |
|------|--------------|-----------|-----------|
| **Automática (cero código)** | Usa agentes que instrumentan dinámicamente sin modificar el código fuente. | Fácil de implementar; ideal para sistemas existentes. | Limitaciones en cobertura y personalización. |
| **Bibliotecas de instrumentación** | Añaden soporte OTel a marcos sin soporte nativo. | Extienden frameworks populares. | Dependencia de mantenimiento y compatibilidad. |
| **Manual** | Inserta directamente llamadas a las API de OTel en el código. | Control total y granularidad. | Mayor esfuerzo de implementación. |

---

## **7. Conclusión**

La observabilidad es una disciplina esencial para comprender el estado y rendimiento de los sistemas distribuidos.  
**OpenTelemetry** representa un paso importante hacia un ecosistema **abierto, interoperable y estandarizado** para la telemetría.

Gracias a su protocolo **OTLP**, su **recopilador flexible** y su **instrumentación multiplataforma**, OTel permite una integración fluida con múltiples herramientas y backends.  

Emitir telemetría en OTLP significa que las aplicaciones instrumentadas son compatibles con innumerables soluciones de observabilidad, fomentando la **consistencia**, la **eficiencia** y la **colaboración entre herramientas**.
