
# StadisticsML

**StadisticsML** es una librería de Python diseñada para facilitar el uso de modelos de aprendizaje automático, específicamente redes neuronales y máquinas de soporte vectorial (SVR), con un enfoque en la predicción y análisis de datos. Esta librería permite al usuario crear modelos personalizables, ajustar hiperparámetros y obtener predicciones y evaluaciones del rendimiento.

## Características

- **Red Neuronal Personalizable**: Permite crear redes neuronales con múltiples capas y activaciones, especificar el número de épocas y la función de optimización.
- **SVR**: Implementación de la máquina de soporte vectorial para regresión, con fácil ajuste de parámetros como el valor de `C`, `gamma` y `epsilon`.
- **Evaluación de Modelos**: Genera métricas de rendimiento como el MSE y RMSE para evaluar la precisión de los modelos entrenados.
- **Interfaz Sencilla**: Funciones fáciles de usar para entrenar modelos y hacer predicciones sobre datos nuevos.

## Instalación

Para instalar la librería, utiliza el siguiente comando de `pip`:

```bash
pip install StadisticsML
```

## Requisitos

- `numpy`
- `scipy`
- `scikit-learn`
- `tensorflow`
  
Estos paquetes se instalarán automáticamente como dependencias cuando instales **StadisticsML**.

## Funciones

### 1. **Red Neuronal Personalizable** (`train_neural_network`)

Esta función permite al usuario crear y entrenar una red neuronal para regresión. Los parámetros ajustables incluyen:

- **X**: Datos de entrada para el entrenamiento.
- **y**: Etiquetas o resultados esperados.
- **hidden_layers_config**: Configuración de las capas ocultas con el número de neuronas y funciones de activación.
- **output_neurons**: Número de neuronas en la capa de salida.
- **output_activation**: Función de activación para la capa de salida.
- **optimizer**: Optimizador a utilizar (e.g., `adam`, `sgd`).
- **loss**: Función de pérdida a utilizar (e.g., `mean_squared_error`).
- **metrics**: Métricas adicionales para evaluar el modelo (e.g., `mae`, `mse`).
- **epochs**: Número de épocas para el entrenamiento.
- **test_size**: Porcentaje de los datos destinados a la prueba.
- **random_state**: Semilla para la aleatorización.

### Ejemplo:

```python
from StadisticsML import train_neural_network

# Datos de ejemplo
X = [[1], [2], [3], [4], [5]]
y = [1.1, 2.0, 2.9, 4.0, 5.1]

# Configuración de las capas ocultas: [(neuronas, función de activación)]
hidden_layers_config = [(12, 'relu'), (8, 'relu')]

# Entrenar la red neuronal
model, history, test_loss, predictions = train_neural_network(
    X=X, y=y, 
    hidden_layers_config=hidden_layers_config,
    epochs=100,
    test_size=0.2,
    random_state=42
)

print("Predicciones:", predictions)
print("Test Loss:", test_loss)
```

### 2. **Máquina de Soporte Vectorial para Regresión (SVR)** (`train_svr`)

Esta función entrena un modelo de soporte vectorial para regresión utilizando parámetros personalizables.

- **X**: Datos de entrada para el entrenamiento.
- **y**: Etiquetas o resultados esperados.
- **C**: Parámetro de penalización.
- **gamma**: Coeficiente de la función kernel.
- **epsilon**: Margen de tolerancia.
- **test_size**: Porcentaje de los datos destinados a la prueba.

### Ejemplo:

```python
from StadisticsML import train_svr

# Datos de ejemplo
X = [[1], [2], [3], [4], [5]]
y = [1.1, 2.0, 2.9, 4.0, 5.1]

# Entrenar el modelo SVR
mse, rmse, predictions = train_svr(X=X, y=y, C=100, gamma=0.001, epsilon=0.001, test_size=0.2)

print("Predicciones SVR:", predictions)
print("RMSE:", rmse)
```

## Contribución

Si deseas contribuir a este proyecto, por favor sigue estos pasos:

1. Haz un fork del repositorio.
2. Crea una nueva rama (`git checkout -b feature/nueva-funcionalidad`).
3. Realiza tus cambios y haz commit de ellos (`git commit -am 'Agrega nueva funcionalidad'`).
4. Haz push a la rama (`git push origin feature/nueva-funcionalidad`).
5. Abre un pull request.

**Contribución esperada:** Implementación de más modelos de aprendizaje automático.

## Licencia

Este proyecto está bajo la licencia **MIT**. Para más detalles, consulta el archivo [LICENSE](LICENSE).

## Contacto

- **Autor**: Jorge Eduardo Londoño Arango
- **Email**: [joelondonoar@unal.edu.co](mailto:joelondonoar@unal.edu.co) - [jorge.nebulanoir@gmail.com](mailto:jorge.nebulanoir@gmail.com)
