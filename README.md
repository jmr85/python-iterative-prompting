# Introducción

IntelliTest es un proyecto que utiliza modelos de inteligencia artificial generativa, como ChatGPT-3.5, para agilizar y mejorar el proceso de generación de casos de prueba de software. Combina la capacidad de la IA para generar ideas y redacciones preliminares con la revisión y validación por parte de expertos humanos. 

Sigue una metodología ágil e iterativa, donde los prompts se refinan continuamente para obtener casos de prueba de alta calidad que cubran todos los escenarios relevantes. Esto permite optimizar recursos, aumentar la eficiencia en pruebas sin comprometer la calidad, reduciendo costos y acelerando el time-to-market.

## Nombre del proyecto  

IntelliTest: Generación de Casos de Prueba Asistida por Inteligencia Artificial

## Presentación del problema a abordar

En la creacion de Test Cases surge a veces problema de como comenzar a redactar los casos de prueba, eso provoca perdida de tiempo productivo. Para solucionar el problema viene muy bien los modelos de IA generativa, como el de chat-gpt, para ayudar a tener un brainstorming o semilla de como redactar los Test Case y ahorrando tiempo de trabajo. Porque pasa tambien, en la realidad, que en el area de Testing, al surgir un nuevo requerimiento casi siempre lo primero que se hace es buscar Test Cases viejos o de Base para luego comenzar a escribir las pruebas, que mejor ieda que usar las herramientas de inteligencia artificial para ahorrarnos ese trabajo, o ayudar a acelerar esa etapa de brainstorning o modo borrador.

## Desarrollo de la propuesta de solución

La solución propuesta se vincula directamente con el desarrollo y aplicación de modelos de inteligencia artificial (IA) generativa, como ChatGPT. Estos modelos de IA están entrenados con grandes cantidades de datos y pueden generar texto coherente y relevante sobre una amplia gama de temas.

En este caso, se utilizarán prompts (instrucciones o consultas) dirigidos al modelo de IA para generar ideas y redacciones iniciales de casos de prueba (Test Cases) a partir de una descripción del requerimiento o funcionalidad a probar. Los prompts podrían tener la siguiente estructura:

Etapa de recopilación de información: "Dado el siguiente requerimiento/funcionalidad [descripción detallada], proporciona una lista de posibles casos de prueba que deberían considerarse para validar su correcto funcionamiento".

Etapa de generación de casos de prueba: "Para cada uno de los casos de prueba identificados en la etapa anterior, genera una redacción inicial que incluya precondiciones, pasos a seguir y resultados esperados".

Etapa de refinamiento: "Revisa y mejora las redacciones de los casos de prueba generados, asegurándote de que sean claros, completos y cubran todos los escenarios relevantes".

Estos prompts pueden ajustarse y refinarse según sea necesario para obtener los mejores resultados posibles del modelo de IA.

## Justificación de la viabilidad del proyecto 

El proyecto propuesto es técnicamente viable debido a la disponibilidad de modelos de IA generativa potentes, como ChatGPT, que pueden ser accedidos a través de APIs o interfaces web. Estos modelos han demostrado su capacidad para generar texto coherente y relevante en diversos dominios, lo que los hace adecuados para la tarea de generación de casos de prueba.
Además, el tiempo y los recursos requeridos para implementar esta solución son relativamente bajos. Una vez que se han definido los prompts adecuados, la generación de casos de prueba puede realizarse de manera rápida y eficiente utilizando el modelo de IA. Esto representa un ahorro significativo de tiempo y esfuerzo en comparación con el proceso manual de redacción de casos de prueba desde cero.
Si bien la solución propuesta no sustituye completamente la revisión y refinamiento manual de los casos de prueba generados, sí tiene el potencial de agilizar y facilitar el proceso, lo que se traduce en un aumento de la productividad y una reducción de los costos asociados a esta tarea.

# Objetivos

El proyecto IntelliTest tiene como objetivo principal optimizar y mejorar el proceso de generación de casos de prueba mediante el uso de inteligencia artificial. Sus objetivos específicos son:

- Generar Test Cases basada en requerimientos de software a modo de brainstorming o seed ya que a veces al principio cuesta comenzar a redactar los Test Cases, agilizando la creación de casos de prueba, reduciendo tiempos y esfuerzos.
- Convertir la descripción textual en Test Cases utilizando la API de OpenAI.
- Aumentar la productividad y eficiencia del equipo de pruebas.

# Metodología

1. Recopilación de Datos: Obtener información sobre un requerimiento particular de
algún nuevo feature.
2. Procesamiento de Texto: Utilizar GPT-3.5 para generar Test Cases del
requerimiento de software como un brainstorning seed o brainstorming.


El proyecto se llevará a cabo mediante una metodología ágil e iterativa que combina la generación de casos de prueba asistida por IA con la revisión y validación humana. Los pasos clave son:

1. Análisis de requerimientos y definición de prompts iniciales.
2. Generación de casos de prueba iniciales con un modelo de IA como ChatGPT-3.5.  
3. Revisión y refinamiento iterativo de los casos de prueba por el equipo humano, realimentando al modelo de IA.
4. Validación, documentación y ejecución final de los casos de prueba refinados.

Esta metodología aprovecha las capacidades de la IA para agilizar el proceso, mientras mantiene el control y supervisión humana para asegurar la calidad. Se justifica por el ahorro de tiempo, la combinación de IA y experiencia humana, y la adaptabilidad a las necesidades del proyecto.

# Herramientas y tecnologías

En cuanto a las técnicas de prompting que se utilizarán, se emplearán diversas estrategias para obtener los mejores resultados posibles del modelo de IA generativa:

- Prompts descriptivos y detallados: Se proporcionarán prompts que incluyan detalles completos sobre el requerimiento o funcionalidad a probar. Esto ayudará al modelo a comprender mejor el contexto y generar casos de prueba más precisos y relevantes.

- Ejemplos de referencia: Se incluirán ejemplos de casos de prueba bien redactados como parte de los prompts. Esto permitirá al modelo comprender mejor el formato y la estructura esperados, lo que mejorará la calidad de las redacciones generadas.

- Iteración y refinamiento: Se utilizará un enfoque iterativo, donde los prompts iniciales se irán refinando y ajustando en función de los resultados obtenidos. Esto permitirá optimizar gradualmente la calidad de los casos de prueba generados.

- Prompts específicos por etapa: Se utilizarán prompts diferentes para cada etapa del proceso (recopilación de información, generación de casos de prueba y refinamiento). Esto permitirá enfocar los prompts en las tareas específicas de cada etapa, lo que mejorará la eficiencia y la precisión de los resultados.

Estas técnicas de prompting se han seleccionado con base en las mejores prácticas y recomendaciones para el uso efectivo de modelos de IA generativa. Al combinar estas estrategias, se espera obtener casos de prueba de alta calidad, completos y relevantes, lo que maximizará los beneficios de utilizar esta solución basada en IA.

# Implementación

```python
#Import openAI dependences (module)
import os
from openai import OpenAI
#Add our API Key copied from openAI page
client = OpenAI(
    api_key='your_key',
)


def generar_casos_prueba(context, requerimiento, casos_prueba_iniciales):
    #prompt (text/user's question)
    prompt = f"Requerimiento: {requerimiento}\n\nCasos de prueba iniciales: {casos_prueba_iniciales}\n\nMejora y expande los casos de prueba. Para cada uno de los casos de prueba identificados en la etapa anterior, genera una redacción inicial que incluya precondiciones, pasos a seguir y resultados esperados"
    response = client.chat.completions.create(
        messages=[
            {"role": "system", "content": context},
            {"role": "user", "content": prompt}
        ],
        model="gpt-3.5-turbo",
        max_tokens=1024
    )
    
    casos_prueba_mejorados = response.choices[0].message.content.strip()
    return casos_prueba_mejorados

def main():

    #Make the context of our prompt envoirement
    context = """
         Ingeniero de pruebas de software: Diseña y ejecuta planes de prueba completos para software.
    """
    
    
    requerimiento = "Desarrollar una pantalla de inicio de sesión para que los usuarios puedan acceder a una página web. La pantalla debe solicitar un nombre de usuario y una contraseña, y validar que los datos ingresados sean correctos. Si los datos son válidos, el usuario debe ser redirigido a la página principal de la aplicación web."

    # Prompt inicial para generar casos de prueba
    prompt_inicial = f"Dado el siguiente requerimiento: {requerimiento}\n\nGenera una lista de posibles casos de prueba que deberían considerarse para validar su correcto funcionamiento."

    # Obtener casos de prueba iniciales
    response = client.chat.completions.create(
        messages=[
            {"role": "system", "content": context},
            {"role": "user", "content": prompt_inicial}
        ],
        model="gpt-3.5-turbo",
        max_tokens=1024
    )
    
    casos_prueba_iniciales = response.choices[0].message.content.strip()
    print("Casos de prueba iniciales:\n", casos_prueba_iniciales)

    # Iteración y refinamiento de los casos de prueba
    for i in range(2):
        casos_prueba_mejorados = generar_casos_prueba(context, requerimiento, casos_prueba_iniciales)
        print(f"\nIteración {i + 1}:\n", casos_prueba_mejorados)
        casos_prueba_iniciales = casos_prueba_mejorados

if __name__ == "__main__":
    main()
```


```md
Casos de prueba iniciales:
 1. Caso de prueba positivo: Ingresar un nombre de usuario y contraseña válidos y verificar que se redirija a la página principal.
2. Caso de prueba negativo: Ingresar un nombre de usuario válido pero una contraseña inválida y verificar que se muestre un mensaje de error.
3. Caso de prueba negativo: Ingresar un nombre de usuario inválido y una contraseña válida y verificar que se muestre un mensaje de error.
4. Caso de prueba negativo: Dejar en blanco tanto el campo de nombre de usuario como el de contraseña y verificar que se muestren mensajes de error para ambos campos.
5. Caso de prueba negativo: Ingresar caracteres especiales en el campo de nombre de usuario y verificar que se muestre un mensaje de error.
6. Caso de prueba negativo: Ingresar una contraseña corta o demasiado larga y verificar que se muestre un mensaje de error.
7. Caso de prueba negativo: Intentar iniciar sesión demasiadas veces con datos incorrectos y verificar que se bloquee la cuenta temporalmente.
8. Caso de prueba negativo: Intentar iniciar sesión con un usuario que se encuentre deshabilitado y verificar que se muestre un mensaje apropiado.
9. Caso de prueba negativo: Intentar iniciar sesión sin conexión a internet y verificar que se muestre un mensaje de error indicando la falta de conexión.
10. Caso de prueba de rendimiento: Probar la velocidad de respuesta al intentar iniciar sesión con diferentes niveles de tráfico de red y verificar que sea aceptable.

Iteración 1:
 Además de los casos de prueba iniciales mencionados anteriormente, se pueden incluir algunos casos de prueba adicionales:

11. Caso de prueba positivo: Ingresar un nombre de usuario con mayúsculas y minúsculas combinadas y una contraseña válida, y verificar que se redirija a la página principal.
   
   - Precondición: La página de inicio de sesión está cargada y lista para recibir datos.
   - Paso a seguir: Ingresar un nombre de usuario con combinación de mayúsculas y minúsculas, una contraseña válida y hacer clic en el botón de iniciar sesión.
   - Resultado esperado: El usuario es redirigido correctamente a la página principal de la aplicación web.

12. Caso de prueba negativo: Intentar iniciar sesión con un nombre de usuario que está en blanco y una contraseña válida, y verificar que se muestre un mensaje de error.

   - Precondición: La página de inicio de sesión está cargada y lista para recibir datos.
   - Paso a seguir: Dejar en blanco el campo de nombre de usuario, ingresar una contraseña válida y hacer clic en el botón de iniciar sesión.
   - Resultado esperado: Se muestra un mensaje de error indicando que el campo de nombre de usuario no puede estar vacío.

13. Caso de prueba negativo: Intentar iniciar sesión con un nombre de usuario válido pero con espacios en blanco al principio o al final y una contraseña válida, y verificar que se redireccione a la página principal.

   - Precondición: La página de inicio de sesión está cargada y lista para recibir datos.
   - Paso a seguir: Ingresar un nombre de usuario con espacios en blanco al principio o al final, una contraseña válida y hacer clic en el botón de iniciar sesión.
   - Resultado esperado: El sistema elimina los espacios en blanco y redirige al usuario a la página principal.

14. Caso de prueba negativo: Introducir caracteres especiales en el campo de contraseña y verificar que se muestre un mensaje de error.

   - Precondición: La página de inicio de sesión está cargada y lista para recibir datos.
   - Paso a seguir: Ingresar un nombre de usuario válido, una contraseña con caracteres especiales y hacer clic en el botón de iniciar sesión.
   - Resultado esperado: Se muestra un mensaje de error indicando que la contraseña no puede contener caracteres especiales.

15. Caso de prueba de seguridad: Intentar realizar un ataque de fuerza bruta con múltiples intentos de inicio de sesión y verificar que se bloquee la cuenta temporalmente.

   - Precondición: La página de inicio de sesión está cargada y lista para recibir datos.
   - Paso a seguir: Introducir un nombre de usuario válido pero con contraseñas incorrectas de forma repetida.
   - Resultado esperado: Después de un cierto número de intentos fallidos, la cuenta debe quedar bloqueada temporalmente y mostrar un mensaje indicando el bloqueo.

Estos casos de prueba adicionales permiten cubrir aspectos específicos de funcionalidad y seguridad que pueden ser críticos para la correcta operación de la pantalla de inicio de sesión en la aplicación web.

Iteración 2:
 16. Caso de prueba negativo: Ingresar un nombre de usuario válido pero una contraseña incorrecta y verificar que se muestre un mensaje de error.

   - Precondición: La página de inicio de sesión está cargada y lista para recibir datos.
   - Paso a seguir: Ingresar un nombre de usuario válido, una contraseña incorrecta y hacer clic en el botón de iniciar sesión.
   - Resultado esperado: Se muestra un mensaje de error indicando que la contraseña ingresada es incorrecta.

17. Caso de prueba negativo: Intentar iniciar sesión con un nombre de usuario inválido y una contraseña válida, y verificar que se muestre un mensaje de error.

   - Precondición: La página de inicio de sesión está cargada y lista para recibir datos.
   - Paso a seguir: Ingresar un nombre de usuario inválido, una contraseña válida y hacer clic en el botón de iniciar sesión.
   - Resultado esperado: Se muestra un mensaje de error indicando que el nombre de usuario ingresado es inválido.

18. Caso de prueba negativo: Dejar en blanco tanto el campo de nombre de usuario como el de la contraseña y verificar que se muestren mensajes de error correspondientes a cada campo.

   - Precondición: La página de inicio de sesión está cargada y lista para recibir datos.
   - Paso a seguir: Dejar en blanco tanto el campo de nombre de usuario como el de contraseña y hacer clic en el botón de iniciar sesión.
   - Resultado esperado: Se muestran mensajes de error indicando que ambos campos no pueden estar vacíos.

19. Caso de prueba de usabilidad: Comprobar que al presionar la tecla "Enter" después de ingresar los datos, el formulario se envíe y se intente realizar el inicio de sesión.

   - Precondición: La página de inicio de sesión está cargada y lista para recibir datos.
   - Paso a seguir: Ingresar un nombre de usuario válido, una contraseña válida y presionar la tecla "Enter".
   - Resultado esperado: El formulario se envía y se intenta realizar el inicio de sesión de manera habitual.

20. Caso de prueba de recuperación de contraseña: Verificar que al hacer clic en un enlace de "¿Olvidó su contraseña?" se presente un formulario para restablecer la contraseña.

   - Precondición: La página de inicio de sesión está cargada y lista para recibir datos.
   - Paso a seguir: Hacer clic en el enlace de "¿Olvidó su contraseña?" y completar el formulario para restablecer la contraseña.
   - Resultado esperado: Se muestra un formulario de recuperación de contraseña y se puede completar el proceso satisfactoriamente.

Estos casos de prueba adicionales permiten cubrir más escenarios de uso y funcionalidades relacionadas con la pantalla de inicio de sesión, lo que contribuye a una mayor calidad y robustez de la misma.
```


