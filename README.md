# Operaciones Morfológicas en Imágenes 3D (binvox)

Este programa implementa operaciones morfológicas básicas (erosión y dilatación) para procesamiento de imágenes 3D en formato binvox.

## Funcionalidades principales

El programa ofrece dos operaciones morfológicas fundamentales para volúmenes 3D:

1. **Erosión 3D**: Elimina voxeles en la superficie de los objetos
2. **Dilatación 3D**: Añade voxeles a la superficie de los objetos

## Estructura del código

### Funciones principales

1. **erosion(imgArit, ariOb)**:
   - Aplica erosión 3D usando un elemento estructurante cúbico
   - Utiliza padding para manejar bordes
   - Compara cada subvolumen con el elemento estructurante
   - Conserva solo los voxeles donde coinciden completamente

2. **dilatacion(imgArit, ariOb)**:
   - Aplica dilatación 3D usando un elemento estructurante cúbico
   - Utiliza padding con valor 255 para bordes
   - Expande los voxeles activos según el elemento estructurante
   - Conserva cualquier coincidencia parcial

### Flujo del programa

1. Carga una imagen 3D en formato binvox (de entre 3 opciones predefinidas)
2. Crea un elemento estructurante 3x3x3
3. Solicita al usuario:
   - Número de iteraciones para la operación
   - Tipo de operación morfológica (1: erosión, 2: dilatación)
4. Aplica la operación seleccionada el número de veces especificado
5. Guarda los resultados en un archivo de texto

## Uso

1. Ejecutar el programa
2. Seleccionar una imagen 3D (0-2)
3. Especificar número de iteraciones
4. Elegir tipo de operación (1-2)
5. El programa generará un archivo .txt con los datos procesados

## Requisitos

- Python 3.x
- Bibliotecas:
  - NumPy (`numpy`)
  - Tkinter (`tkinter`)
  - BinvoxR (`BinvoxR` - para lectura de archivos binvox)
  - re (`re`)

## Parámetros importantes

- **ariOb**: Elemento estructurante 3D (3x3x3 por defecto)
- **cantSelec**: Número de iteraciones para la operación
- **imgArit**: Matriz 3D que representa el volumen binario
- **padding**: Se añade para manejar correctamente los bordes

## Formatos de archivo

- **Entrada**: Archivos .binvox (formato compacto para modelos 3D voxelizados)
- **Salida**: Archivos .txt con matrices 3D que representan el volumen procesado

## Notas importantes

1. Las imágenes deben estar en la carpeta `3D` con nombres específicos (00.binvox, 01.binvox, 02.binvox)
2. El elemento estructurante es fijo (cubo 3x3x3 de unos)
3. Los resultados se guardan como matrices de:
   - 1: Voxel activo
   - 0: Voxel inactivo
4. Para visualizar los resultados se necesitaría software adicional de visualización 3D

## Limitaciones

- Solo trabaja con archivos binvox predefinidos
- No incluye visualización gráfica de los resultados 3D
- El elemento estructurante no es configurable por el usuario
