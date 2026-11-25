# Banca en línea y aplicación móvil — “Banco Pichincha”

**Componente Práctico 2 (CP2)** · Unidades 3 y 4: Análisis de Requerimientos, Pruebas de Software y Control de Versiones.

## Datos del Grupo
* **Grupo:** Grupo D
* **Integrantes:**
  * Josue Chiquito Yanez
  * Eri Pinto
  * Jonathan Gerardo
* **Fecha de entrega:** 25/11/2026

## Introducción
Este proyecto corresponde al Componente Práctico 2 (Unidades 3 y 4) y aborda el análisis de requerimientos, pruebas de software y control de versiones para la plataforma de banca en línea y aplicación móvil de la institución ficticia **Banco Pichincha**. El sistema busca facilitar operaciones financieras cotidianas e integrar un motor automatizado de ofertas de crédito. Ante riesgos identificados de opacidad algorítmica, posibles sesgos y acumulación indefinida de datos, el objetivo es proveer una plataforma segura, confiable y centrada en el usuario que equilibre la innovación analítica con principios de explicabilidad, trazabilidad y minimización de datos personales.

## Análisis de Requisitos y Casos de Prueba

| ID | Tipo de requisito | Descripción del requisito | Caso de prueba propuesto | Resultado esperado |
| :--- | :--- | :--- | :--- | :--- |
| **RF-01** | Funcional | El sistema debe permitir a los clientes autenticados realizar transferencias interbancarias, actualizando de forma inmediata el saldo disponible y registrando la operación en el historial de movimientos. | Iniciar sesión en una cuenta con saldo de $500,00, ingresar una transferencia interbancaria de $120,00 hacia una cuenta destino válida y confirmar la transacción. | La transferencia se ejecuta correctamente, el saldo disponible se actualiza a $380,00, se emite un comprobante digital y el débito queda visible en el historial de movimientos. |
| **RF-02** | Funcional | El sistema debe analizar automáticamente el historial de transacciones, la frecuencia de depósitos y los pagos realizados para evaluar la elegibilidad crediticia y emitir ofertas personalizadas. | Ejecutar el motor de evaluación con dos perfiles de prueba: Perfil A (depósitos constantes y pagos puntuales durante 12 meses) y Perfil B (ingresos irregulares y pagos vencidos). | El sistema clasifica al Perfil A como elegible y genera una oferta de crédito acorde a su perfil financiero, mientras que al Perfil B lo descarta sin asignar una oferta activa. |
| **RF-03** | Funcional | El sistema debe mostrar al cliente una explicación comprensible de los criterios principales que determinaron las condiciones o el descarte de una oferta de crédito automatizada. | Acceder desde la aplicación al detalle de la evaluación crediticia utilizando una cuenta con oferta aprobada y otra cuenta descartada por el sistema. | La aplicación presenta los factores determinantes (como estabilidad de depósitos o comportamiento de pago) en lenguaje claro, sin exponer el código ni la lógica propietaria del modelo. |
| **RNF-01** | No funcional | El sistema debe garantizar la privacidad y minimización de datos, conservando únicamente la información financiera necesaria para fines declarados, durante plazos definidos y con consentimiento del cliente. | Realizar una verificación teórica sobre el flujo de datos y permisos cuando un cliente revoca su autorización para el uso de su información en modelos futuros de análisis. | El sistema registra la revocación, excluye los datos del cliente de futuros entrenamientos analíticos y programa la anonimización o eliminación de registros que excedan el plazo legal. |
| **RNF-02** | No funcional | Toda comunicación entre la aplicación móvil y los servidores bancarios debe contar con cifrado en tránsito (TLS 1.3 o superior) y autenticación multifactor (MFA) para operaciones sensibles. | Simular una transferencia interbancaria monitoreando el tráfico de red e intentar confirmar la operación omitiendo el código de verificación de segundo factor (OTP). | Los paquetes interceptados resultan ilegibles por estar cifrados y el sistema bloquea la operación hasta que el usuario ingrese un código OTP válido. |

### Criterio de trazabilidad
Los requisitos **RF-01** y **RF-02** cubren la operatividad esencial de la banca digital y su motor de ofertas crediticias; **RF-03** y **RNF-01** atienden directamente los riesgos de opacidad algorítmica y acumulación indiscriminada de datos; y **RNF-02** resguarda la integridad y confidencialidad de las transacciones financieras.

## Documentación Formal
Puedes consultar el documento completo del Componente Práctico 2 (incluyendo datos generales, planteamiento detallado del problema y evidencia de colaboradores en GitHub) en el siguiente enlace:

* [CP2_Requerimientos_y_Pruebas.pdf](./CP2_Requerimientos_y_Pruebas.pdf)
