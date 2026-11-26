<div align="center">

# 🏦 Banca en Línea y Aplicación Móvil — “Banco Pichincha”

**Componente Práctico 2 (CP2) · Unidades 3 y 4**  
*Análisis de Requerimientos, Pruebas de Software y Control de Versiones*

![Estado](https://img.shields.io/badge/Estado-Completado-brightgreen?style=for-the-badge)
![Grupo](https://img.shields.io/badge/Grupo-D-blue?style=for-the-badge)
![Modalidad](https://img.shields.io/badge/Modalidad-Grupal-orange?style=for-the-badge)
![Fecha](https://img.shields.io/badge/Entrega-25%2F11%2F2026-informational?style=for-the-badge)

</div>

---

## 📖 Introducción

Este proyecto corresponde al Componente Práctico 2 (Unidades 3 y 4) y aborda el análisis de requerimientos, pruebas de software y control de versiones para la plataforma de banca en línea y aplicación móvil de la institución ficticia **Banco Pichincha**. El sistema busca facilitar operaciones financieras cotidianas e integrar un motor automatizado de ofertas de crédito. Ante riesgos identificados de opacidad algorítmica, posibles sesgos y acumulación indefinida de datos, el objetivo es proveer una plataforma segura, confiable y centrada en el usuario que equilibre la innovación analítica con principios de explicabilidad, trazabilidad y minimización de datos personales.

---

## 🎯 Descripción del Problema y Objetivo del Sistema

### ⚠️ 2.1 Descripción del problema

La institución financiera ficticia **Banco Pichincha** desarrolla una plataforma de banca en línea y aplicación móvil orientada a facilitar operaciones financieras cotidianas, tales como la consulta de saldos, transferencias interbancarias, pago de servicios y revisión del historial de movimientos. Como evolución del producto, la entidad incorpora un sistema automatizado de evaluación que procesa el historial transaccional, la frecuencia de depósitos, los pagos efectuados y otros patrones de comportamiento digital para identificar qué clientes pueden recibir ofertas de crédito.

Durante la fase de pruebas, el equipo técnico identifica una problemática crítica: el sistema otorga automáticamente mejores condiciones crediticias a determinados usuarios y descarta a otros sin ofrecer una explicación clara ni verificable de los criterios aplicados. A esto se suma la directriz gerencial de mantener el funcionamiento interno bajo reserva, desplegar la funcionalidad sin transparentar los factores de decisión al cliente y conservar de manera indefinida la totalidad de los datos disponibles para futuros modelos analíticos. Esta situación genera riesgos relevantes en materia de transparencia, posibles sesgos algorítmicos, vulneración de la privacidad financiera y pérdida de confianza por parte de los usuarios.

### 🚀 2.2 Objetivo del sistema

> Proveer una plataforma digital de banca en línea y aplicación móvil segura, confiable y centrada en el usuario que garantice la ejecución precisa de operaciones financieras básicas, integrando un módulo automatizado de ofertas de crédito bajo principios de explicabilidad, trazabilidad y minimización de datos personales. De este modo, el sistema equilibra la innovación analítica de la entidad con el derecho del cliente a comprender las decisiones automatizadas que afectan su información y acceso financiero.

---

## 👥 Equipo de Desarrollo (Grupo D)

| Integrante | Rol en el Repositorio |
| :--- | :--- |
| 👨‍💻 **Josue Chiquito Yanez** | Colaborador / Análisis y Pruebas |
| 👨‍💻 **Eri Pinto** | Colaborador / Análisis y Pruebas |
| 👨‍💻 **Jonathan Gerardo** | Colaborador / Análisis y Pruebas |

---

## 📋 Análisis de Requisitos y Casos de Prueba

A continuación, se detallan los requisitos funcionales (**RF**) y no funcionales (**RNF**) diseñados para garantizar tanto la operatividad bancaria como la ética, transparencia y seguridad del sistema:

| ID | Tipo | Descripción del Requisito | Caso de Prueba Propuesto | Resultado Esperado |
| :---: | :---: | :--- | :--- | :--- |
| **RF-01** | ⚙️ Funcional | El sistema debe permitir a los clientes autenticados realizar transferencias interbancarias, actualizando de forma inmediata el saldo disponible y registrando la operación en el historial de movimientos. | Iniciar sesión en una cuenta con saldo de \$500,00, ingresar una transferencia interbancaria de \$120,00 hacia una cuenta destino válida y confirmar la transacción. | La transferencia se ejecuta correctamente, el saldo disponible se actualiza a \$380,00, se emite un comprobante digital y el débito queda visible en el historial de movimientos. |
| **RF-02** | ⚙️ Funcional | El sistema debe analizar automáticamente el historial de transacciones, la frecuencia de depósitos y los pagos realizados para evaluar la elegibilidad crediticia y emitir ofertas personalizadas. | Ejecutar el motor de evaluación con dos perfiles de prueba: **Perfil A** (depósitos constantes y pagos puntuales durante 12 meses) y **Perfil B** (ingresos irregulares y pagos vencidos). | El sistema clasifica al Perfil A como elegible y genera una oferta de crédito acorde a su perfil financiero, mientras que al Perfil B lo descarta sin asignar una oferta activa. |
| **RF-03** | ⚙️ Funcional | El sistema debe mostrar al cliente una explicación comprensible de los criterios principales que determinaron las condiciones o el descarte de una oferta de crédito automatizada. | Acceder desde la aplicación al detalle de la evaluación crediticia utilizando una cuenta con oferta aprobada y otra cuenta descartada por el sistema. | La aplicación presenta los factores determinantes (como estabilidad de depósitos o comportamiento de pago) en lenguaje claro, sin exponer el código ni la lógica propietaria del modelo. |
| **RNF-01** | 🛡️ No Funcional | El sistema debe garantizar la privacidad y minimización de datos, conservando únicamente la información financiera necesaria para fines declarados, durante plazos definidos y con consentimiento del cliente. | Realizar una verificación teórica sobre el flujo de datos y permisos cuando un cliente revoca su autorización para el uso de su información en modelos futuros de análisis. | El sistema registra la revocación, excluye los datos del cliente de futuros entrenamientos analíticos y programa la anonimización o eliminación de registros que excedan el plazo legal. |
| **RNF-02** | 🔒 No Funcional | Toda comunicación entre la aplicación móvil y los servidores bancarios debe contar con cifrado en tránsito (TLS 1.3 o superior) y autenticación multifactor (MFA) para operaciones sensibles. | Simular una transferencia interbancaria monitoreando el tráfico de red e intentar confirmar la operación omitiendo el código de verificación de segundo factor (OTP). | Los paquetes interceptados resultan ilegibles por estar cifrados y el sistema bloquea la operación hasta que el usuario ingrese un código OTP válido. |

> 💡 **Criterio de Trazabilidad:**  
> Los requisitos **RF-01** y **RF-02** cubren la operatividad esencial de la banca digital y su motor de ofertas crediticias; **RF-03** y **RNF-01** atienden directamente los riesgos de opacidad algorítmica y acumulación indiscriminada de datos; y **RNF-02** resguarda la integridad y confidencialidad de las transacciones financieras.

---

