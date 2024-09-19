# ChatBot: Simple Conversational AI

## Descripción

Este proyecto es un chatbot sencillo que responde a entradas de texto utilizando un archivo `intents.json` para reconocer patrones y generar respuestas apropiadas. Está desarrollado en **Python** utilizando **TensorFlow** y **Keras**, y se entrena sobre datos simples basados en patrones y etiquetas de intención.

**Miau, somos el equipo Michis Bitchis** y este proyecto refleja la fase inicial de nuestro desarrollo en el campo de IA conversacional.

## Archivos Principales

- **ChatBot.ipynb**: Contiene el código para cargar datos, preprocesar texto, entrenar el modelo de chatbot y realizar predicciones.
- **intents.json**: Archivo de datos donde se definen los patrones, las etiquetas (intents) y las respuestas que utiliza el chatbot para interactuar con los usuarios.
  
---

## Métodos Utilizados

### 1. **Preprocesamiento de Texto**
   - **Tokenización**: Se dividen las frases de entrada en tokens o palabras individuales utilizando `nltk.word_tokenize`.
   - **Lematización**: Las palabras se reducen a su raíz o forma base utilizando `WordNetLemmatizer` para tratar variaciones de la misma palabra (ej. "gatos" -> "gato").
   - **Eliminar Puntuación**: Se elimina cualquier signo de puntuación para simplificar el análisis.

### 2. **Modelo Bag of Words (BoW)**
   - Se genera un vector binario para cada frase de entrada, donde se indica si una palabra del vocabulario está presente o no. Esto sirve como entrada para el modelo de red neuronal.

### 3. **Entrenamiento de la Red Neuronal**
   - **Arquitectura del Modelo**:
     - **Capa densa**: 128 neuronas con activación ReLU.
     - **Dropout**: 50% de dropout para prevenir sobreajuste.
     - **Capa densa**: 64 neuronas con activación ReLU.
     - **Capa de salida**: Neuronas equivalentes al número de etiquetas, con activación Softmax para generar probabilidades sobre las posibles intenciones.
   - **Optimización**: El modelo utiliza el optimizador **Adam** y se entrena durante 150 épocas.

### 4. **Predicción y Respuesta**
   - Después del entrenamiento, el chatbot utiliza el modelo para hacer predicciones sobre el intento de una frase ingresada por el usuario. Devuelve la respuesta correspondiente del archivo `intents.json`.

---

## Cómo Usar

1. Sube el archivo `ChatBot.ipynb` a Google Colab o ejecútalo localmente.
2. Asegúrate de que el archivo `intents.json` esté en el mismo directorio que tu notebook.
3. Ejecuta todas las celdas de la notebook para cargar el modelo, preprocesar los datos y entrenar el chatbot.
4. Una vez entrenado, puedes interactuar con el chatbot ingresando frases en la celda final del notebook.

---

## Ejemplo de Interacción

A continuación, se muestra un ejemplo de una interacción con el chatbot donde aún queda claro que el entrenamiento y los datos del archivo `intents.json` necesitan mejorar:

### Entrada del Usuario:
![ChatBot Interaction](./sample_chatbot_interaction.png) 
