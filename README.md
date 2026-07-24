# payphone-prueba
payphone-prueba

## Confirmación temporal para WhatsApp Consultas

`whatsapp-confirm.html` confirma en el navegador los pagos enviados desde
`wa-consultas.macvasquez.com`. La página reutiliza la configuración PayPhone
que ya funciona en `order-status.html`; no modifica `index.html`,
`order-status.html` ni sus flujos actuales.

PayPhone debe recibir como URL de respuesta:

```text
https://pagos.macvasquez.com/whatsapp-confirm.html?orderToken=TOKEN_DE_ORDEN
```

Después de consultar `Button/V2/Confirm`, la página envía el resultado a:

```text
https://wa-consultas.macvasquez.com/api/payments/payphone/confirm
```

Esta integración es temporal: el backend valida la orden, el monto, la moneda,
el identificador del comercio y evita acreditaciones duplicadas, pero recibe
la respuesta PayPhone desde el navegador.
