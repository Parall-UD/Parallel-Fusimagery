# Parallel-Fusimagery

## Descripción

Esta aplicación hace uso de la computación heterogénea Multi-Core (CPU) / Many-Core (GPU) para acelerar el proceso de fusión de imágenes multiespectrales y pancromáticas mediante el uso de la transformada Wavelet Fast Haar.

La fusión permite la combinación y utilización de datos procedentes de fuentes diferentes. La idea es obtener información de “mayor calidad” que la original, la cual dependerá de la aplicación. La fusión de imágenes es una respuesta a la frecuente necesidad de tener en una sola imagen datos de alta resolución espectral y espacial a partir de imágenes de diferente resolución espacial y/o diferentes sensores remotos. La fusión permite obtener información detallada sobre el medio ambiente urbano y rural, útil para una aplicación
específica en diferentes estudios geográficos.

La transformada discreta de Wavelet (TDW), es una transformación lineal que tiene una gran utilidad en el área de procesamiento de señales, para este caso señales bidimensionales. Una de sus principales aplicaciones consiste en separar conjunto de datos en componentes de distinta frecuencia espacial, representados en escalas comunes. El algoritmo (TDW) es utilizado dentro de las estrategias de fusión de imágenes de satélite debido a la alta calidad espectral que caracteriza a las imágenes fusionadas mediante este método
La implementación de la transformada Wavelet, se realizó de la siguiente forma.
La implementación de la fusión de imágenes usando la transformada Wavelet se realiza mediante la descomposición de los componentes Intensidad (I), y la imagen pancromática (PAN).:
• Registrar una composición a color RGB (verdadero color) de la imagen MULT con la PAN, usando el mismo tamaño de píxel de esta última. Transformar la imagen RGB en componentes IHS (Intensidad, matiz y saturación) de la imagen MULTI.
• Aplicar el concepto de Transformada Wavelet al componente I, iterativamente hasta el segundo nivel descomposición, obteniendo de esta manera los siguientes coeficientes de aproximación y detalle. cA2i coeficientes de aproximación que contienen
la información espectral de la componente I, cV2i, cH2i, cD2i, cV1i, cH1i, cD1i, coeficientes de detalle donde se almacena la información espacial de I.
• Aplicar el concepto de la Transformada Wavelet a la imagen PAN hasta el segundo nivel descomposición obteniendo de esta manera los coeficientes de aproximación y detalle. cA2p coeficientes de aproximación que contiene la información espectral de la PAN, cV2p, cH2p, cD2p, cV1p, cH1p y cD1p, coeficientes de detalle donde se almacena la información espacial de la imagen PAN.
• Generar una nueva matriz concatenando los coeficientes cA2i (que almacena la información espectral de la componente I) y los coeficientes de detalle espacial de segundo nivel de la imagen PAN, cV2p, cH2p, cD2p, cV1p, cH1p y cD1p, (que almacena
la información espacial de la imagen PAN). Aplicar la transformada inversa de la Transformada Wavelet a la matriz obtenida en el paso anterior para obtener la nueva componente intensidad (N-INT).
• Generar una nueva composición IHS (N-IHS), uniendo la N-INT (nuevo componente intensidad) junto con las componentes originales de matiz y saturación (obtenidas en el primer paso). Realizar la transformación IHS a RGB, usando la nueva composición N-IHS. De esta manera se obtiene la nueva imagen multiespectral (nueva rgb, N-MULT), que mantiene en menor valor la resolución espectral ganando así la
resolución espacial.

## Manual de Usuario

El manual de usuario realizado para esta aplicación, tiene como finalidad presentar la interacción paso a paso entre el usuario y los scripts. El manual de usuario se encuentra disponible en la siguiente dirección : https://github.com/Parall-UD/Parallel-Fusimagery/blob/master/Manuales/ManualUsuario-Parallel-Fusimagery.pdf

## Manual Técnico

El manual técnico realizado para esta aplicación, tiene como finalidad presentar el proceso de instalación con los componentes necesarios para poder ejecturar cada uno de los scripts. El manual técnico se encuentra disponible en la siguiente dirección : https://github.com/Parall-UD/Parallel-Fusimagery/blob/master/Manuales/ManualTecnico-Parallel-Fusimagery.pdf

## Especificación de Requisitos de Software
Este documento es una Especificación de Requisitos Software (ERS) para el software llamado “Parallel-Fusimagery”. Esta especificación se ha estructurado basándose en las directrices dadas por el estándar IEEE Práctica Recomendada para Especificaciones de Requisitos Software ANSI/IEEE 830, 1998. Este documento se encuentra disponible en la siguiente dirección : https://github.com/Parall-UD/Parallel-Fusimagery/blob/master/Manuales/IEEE-830-Parallel-Fusimagery.pdf

## Video Tutorial
Con el fin de presentar detalladamente el funcionamiento de la aplicación, se realizó un video tutorial donde se presenta la interacción entre el usuario y la plataforma. El video tutorial se encuentra disponible en la siguiente dirección: https://www.youtube.com/watch?v=deytLC8rEcQ&feature=youtu.be
