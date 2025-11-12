# Coche Arduino con Inteligencia Artificial

## Descripción del Proyecto
Este proyecto implementa una red neuronal en un coche Arduino para que pueda conducir de manera autónoma evitando obstáculos. El sistema utiliza machine learning para entrenar una red neuronal que controla los motores del coche.

## Evolución del Proyecto
### Fase Inicial
- Red neuronal en Python con 2 entradas (distancia y posición del obstáculo) y 4 salidas (control de 4 motores).
- Entrenamiento con 9 patrones de entrada.
- Transferencia de los pesos de la red a Arduino para la propagación hacia adelante.

### Fase Mejorada
Se agregaron dos nuevos sensores y una salida:

#### Nuevas Entradas
1. **Sensor de Peso**: Detecta si el coche lleva un paquete.
   - `-1`: Sin paquete
   - `1`: Con paquete

2. **Sensor de Línea**: Detecta si el coche debe seguir una línea.
   - `-1`: No sigue línea
   - `1`: Sigue línea

#### Nueva Salida
- **LED**: Indicador luminoso.
   - `0`: Apagado
   - `1`: Encendido

### Arquitectura de la Red Neuronal Mejorada
- **Capas**: [4, 6, 5] (4 entradas, 6 neuronas en la capa oculta, 5 salidas)
- **Función de activación**: Tangente hiperbólica (tanh)
- **Rango de entrada**: [-1, 1]
- **Rango de salida**: [-1, 1] (luego se redondea a 0 o 1)

### Tablas de Verdad por Miembro del Equipo

#### Miembro 1
- **Lógica del LED**: Se enciende cuando hay peso o cuando está siguiendo una línea.
- [Incluir tabla de verdad del miembro 1]

#### Miembro 2
- **Lógica del LED**: Se enciende solo cuando hay peso, independientemente de la línea.
- [Incluir tabla de verdad del miembro 2]

## Código
El repositorio contiene los siguientes archivos:

- `codigo/red_neuronal_original.py`: Red neuronal original con 2 entradas y 4 salidas.
- `codigo/red_neuronal_mejorada_miembro1.py`: Red neuronal del miembro 1 con 4 entradas y 5 salidas.
- `codigo/red_neuronal_mejorada_miembro2.py`: Red neuronal del miembro 2 con 4 entradas y 5 salidas.
- `codigo/arduino_coche_mejorado/arduino_coche_mejorado.ino`: Código Arduino para el coche con las nuevas funcionalidades.

## Resultados
Las redes neuronales se entrenaron durante 40,000 épocas y mostraron una disminución en el coste, lo que indica un aprendizaje exitoso. Las predicciones de las redes se ajustaron a los valores esperados en la mayoría de los casos.

## Enfoques de Resolución de Problemas
1. **Aprendizaje Supervisado**: Se utilizó un conjunto de datos etiquetados para entrenar la red.
2. **Normalización de Datos**: Las entradas y salidas se normalizaron en el rango [-1, 1].
3. **Backpropagation**: Algoritmo de entrenamiento para ajustar los pesos.
4. **Modularidad**: El código se estructuró en funciones y clases para facilitar su mantenimiento y comprensión.

## Instalación y Uso
1. Clonar el repositorio.
2. Ejecutar los scripts de Python para entrenar las redes neuronales.
3. Cargar el código Arduino en el coche.
4. Asegurarse de que el hardware esté correctamente conectado.

## Hardware Requerido
- Placa Arduino Uno o Mega.
- Shield de expansión de IO.
- Controlador de motor L298N.
- 4 motores DC y ruedas.
- Servo motor SG90.
- Sensor ultrasónico.
- Sensor de peso (simulado).
- Sensor de línea (simulado).
- LED.
- Baterías y chasis.

## Conclusiones
El proyecto demostró la aplicabilidad de las redes neuronales en la robótica móvil, permitiendo que un coche Arduino tome decisiones autónomas. La adición de nuevos sensores y actuadores enriqueció el comportamiento del coche, haciendo que responda a más estímulos del ambiente.

## Futuras Mejoras
- Implementar más sensores (luz, temperatura, etc.).
- Añadir más actuadores (más LEDs, buzzer, etc.).
- Utilizar redes neuronales convolucionales para el procesamiento de imágenes.

## Integrantes del Proyecto
- [Nombre del miembro 1]
- [Nombre del miembro 2]


