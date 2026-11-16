# ddqn-slicer

Algoritmo de ejecución de órdenes con Deep Q-Learning: un agente DDQN aprende a trocear una orden CARE de compra y a reproducir un calendario TWAP sobre datos reales del libro de órdenes de Repsol.

Taller de Aprendizaje por Refuerzo · Máster MIAX (BME)
**Grupo:** Eneko Amezcua · Luis Coello · Eduardo González
Plantilla del taller: Alberto Oteo García y Jesús Sanz del Real

## Contenido

| Ejercicio | Qué se hace |
|---|---|
| 1 | Simulador del libro de órdenes (`BestExecutionEnv`) y entrenamiento completo de un DDQN |
| 2 | Recompensa estilo TWAP, elección motivada de gamma e hiperparámetros |
| 3 | Exploración (epsilon) ligada al aprendizaje del agente, no al número de episodios |
| 4 | Idea B (orden completada en el 90 % de la duración) e Idea C (parada, guardado y reanudación del entrenamiento) |

## Estructura

```
├── data/
│   └── rep_data.pkl                  # datos de Repsol (bins de 5 s)
├── src/
│   ├── agents/dqn.py                 # agente DDQN de la plantilla
│   └── report/report.py              # gráfico de resultados de la plantilla
├── workshop/
│   └── execution_lab_entrega.ipynb   # notebook del taller
└── setup.py                          # dependencias
```

## Instalación

Requiere **Python 3.11**.

```bash
git clone https://github.com/eglezarr/ddqn-slicer.git
cd ddqn-slicer
python3.11 -m venv .venv
source .venv/bin/activate          # Windows: .venv\Scripts\activate
pip install -e .
```

## Ejecución

1. Abrir `workshop/execution_lab_entrega.ipynb` en VS Code o Jupyter.
2. Seleccionar el kernel `.venv`.
3. *Restart* y *Run All*. La ejecución completa tarda unos 15 minutos.

El Ejercicio 4 crea la carpeta `workshop/checkpoints/` con los guardados del entrenamiento. No se sube al repositorio.

Las semillas están fijadas. En otro hardware, TensorFlow puede dar decimales ligeramente distintos sin que cambien las conclusiones.

## Cómo trabajamos en el repositorio

Git no fusiona bien dos cambios simultáneos sobre el mismo notebook, así que lo editamos **por turnos**:

1. Antes de empezar: `git pull`.
2. Avisar al grupo de que se está editando.
3. Al terminar: `git add`, `git commit -m "qué se ha cambiado"` y `git push`.

Para ver los cambios de un notebook celda a celda: `pip install nbdime` y después `nbdiff-web`.
