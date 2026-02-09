🐞 BUG-001 – Error en validación de login con credenciales inválidas

📌 Descripción  
Al ingresar credenciales inválidas en el login de SauceDemo,
el mensaje de error no se muestra de forma consistente.

---

🔁 Pasos para reproducir
1. Ingresar a https://www.saucedemo.com

2. Ingresar usuario inválido
3. Ingresar contraseña inválida
4. Click en "Login"

---

✅ Resultado esperado  
El sistema debería mostrar un mensaje de error indicando
que las credenciales son incorrectas.

---

❌ Resultado actual  
El mensaje de error no se muestra o se muestra de forma inconsistente.

---

🔥 Severidad  
Media

🎯 Prioridad  
Alta

🧠 Justificación  
La severidad es Media porque la funcionalidad de login continúa operativa,
pero la prioridad es Alta debido a que afecta la experiencia del usuario
y la correcta comunicación de errores.

📎 Evidencia  
Durante la ejecución de la prueba el mensaje de error no fue visible
en el primer intento de login, requiriendo refrescar la página.
/<img width="1353" height="730" alt="Captura de pantalla 2026-02-09 a la(s) 18 03 07" src="https://github.com/user-attachments/assets/3f750998-8ac8-4727-a112-352df975e5af" />
