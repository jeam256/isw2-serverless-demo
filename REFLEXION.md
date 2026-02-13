# Reflexión: Pruebas automatizadas y CI

## 1) ¿Qué tipo de error evita el CI?
Evita que se integren cambios que rompen el contrato esperado del sistema (regresiones). Por ejemplo, si alguien cambia la lógica de `api/procesar` (como pasar de `toUpperCase()` a `toLowerCase()`), las pruebas fallan y el pipeline bloquea ese cambio. También evita errores lógicos cubiertos por las pruebas y asegura que el proyecto siga pasando las validaciones automáticamente en cada push.

## 2) ¿Qué tipo de error no evita?
No evita errores que no estén cubiertos por pruebas. Si existe un caso no probado, el CI puede pasar aunque el sistema esté mal para ese escenario. Tampoco detecta por sí solo problemas de rendimiento, seguridad, experiencia de usuario, ni fallos de integración con servicios externos si no se prueban explícitamente.

## 3) ¿Qué pasaría si un equipo ignora el CI?
Se pueden mezclar cambios defectuosos en la rama principal, se rompe la estabilidad del proyecto y se pierde confianza en el repositorio. El equipo termina gastando tiempo arreglando errores después, aparecen fallas en producción con más frecuencia y se vuelve más difícil colaborar porque nadie sabe si el código “actual” funciona realmente.
