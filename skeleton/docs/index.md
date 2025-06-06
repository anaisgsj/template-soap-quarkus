# Servicio SOAP Contract-First en Quarkus

Este proyecto implementa un servicio SOAP en Quarkus utilizando un enfoque **Contract First**, donde el contrato (`WSDL`) define la interfaz del servicio y las clases Java se generan automáticamente a partir de este.

Para mas informacion consulta: (https://docs.quarkiverse.io/quarkus-cxf/dev/user-guide/contract-first-code-first/generate-java-from-wsdl.html#).

---

## Descripción

Este servicio expone una operación SOAP definida en el archivo WSDL ubicado en:

    src/main/resources/wsdl/achivo.wsdl

y utiliza los esquemas XML ubicados en:

    src/main/resources/xsd/archivo.xsd

---

## Estructura del Proyecto

```plaintext
nombre del servicio/
├── src/
│   └── main/
│       ├── java/
│       │   └── package/
│       │       └── service/       # Implementaciones SOAP
│       └── resources/
│           ├── wsdl/              # WSDL y binding.xml (opcional)
│           └── xsd/               # Archivos XSD usados por el WSDL
├── pom.xml                        # Configuración del proyecto y dependencias
├── catalog-info.yaml              # Registro para Backstage
└── docs/
    └── index.md                   # Este archivo de documentación
```

---

## Dependencias clave

- [`quarkus-cxf`](https://quarkiverse.github.io/quarkiverse-docs/quarkus-cxf/dev/index.html): integración de Apache CXF en Quarkus para exponer servicios SOAP.

---

## Cómo correr el proyecto localmente

Ejecuta:

```bash
./mvnw clean compile quarkus:dev
