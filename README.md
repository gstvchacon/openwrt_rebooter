# rebooter.sh

Este script está diseñado para reiniciar un router con una llamada. Puede ser invocado directamente o desde otros scripts, como `openwrt_autoupdate.sh`.

## Cómo funciona

1. **Sin argumentos**: Si el script se ejecuta sin argumentos, registra un mensaje indicando que se recibió una solicitud de reinicio sin argumentos.
2. **Con argumentos**: Si se proporciona un argumento, registra un mensaje indicando el origen del reinicio y procede a reiniciar el sistema.
3. **Registro de eventos**: Todos los eventos se registran en un archivo llamado `rebooter.log`.

## Uso

### Ejecución directa

1. Asegúrate de que el script sea ejecutable:
   ```bash
   chmod +x rebooter.sh
   ```

2. Ejecuta el script:
   - Sin argumentos:
     ```bash
     ./rebooter.sh
     ```
   - Con un argumento (por ejemplo, "manual"):
     ```bash
     ./rebooter.sh manual
     ```

### Integración con otros scripts

Este script puede ser llamado desde otros scripts, como `openwrt_autoupdate.sh`, para automatizar el proceso de reinicio.

## Registro

El script registra los siguientes eventos en el archivo `rebooter.log`:

- **Sin argumentos**:  
  `YYYY-MM-DD-THH:MM:SS: receive reboot without argument`
- **Con argumentos**:  
  `YYYY-MM-DD-THH:MM:SS: reboot from : <argumento>`

## Mejoras potenciales

- Validar los argumentos proporcionados para evitar entradas no deseadas.
- Manejar errores en el proceso de reinicio.
- Rotar o archivar el archivo de registro `rebooter.log` para evitar que crezca indefinidamente.