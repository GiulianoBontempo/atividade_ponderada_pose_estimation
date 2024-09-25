Esse repositório é relativo a ponderada de Pose Estimation da semana 7 do módulo 5.

# Conteúdo

O notebook pose estimation tem como objetivo treinar um modelo para reconhecimento da pose de bovinos.

# Exploração Inicial e Filtragem

O dataset inicialmente baixado tinha diversos animais, mas para fins de praticidade e limitação do escopo, separamos somente as imagens de bovinos. Na análise exploratória percebmos que haviam annotations para 842 imagens de bovinos, mas no arquivo baixado só haviam 200 (gráfico demonstrativo em relação a isso no notebook). Com isso, realizamos umas filtragem a partir da associação dos ids dos annotations com os nomes dos arquivos para guardar somente os annotations que tinham imagens associadas.

# Processamento

Com relação ao processamento, foram desenvolvidas funções para carregar uma imagem a partir de um annotation, visualizar os keypoints para ter uma noção de com o que estavamos lidando, e para gerar anotações no estilo yolo, onde para cada imagem há um arquivo txt associado com a sua classificação, as coordenadas do bounding box e dos keypoints. (As imagens e anotações não estão no github para deixar o repositório o mais leve o possível).

Além das anotações no formato txt, também foi elaborado um arquivo yaml, como é padrão para modelos yolo. O yaml foi elaborado manualmente.

# Escolhas

O modelo escolhido foi o yolov8n-pose, por ter todo o poder e arcabouço dos modelos yolos e ser o mais leve dos Yolo Pose.


# Conclusões

Os resultados foram animadores já que, mesmo utilizando o modelo mais leve de pose estimation do yolov8, e realizando somente 50 épocas de treinamento, atingimos um box loss de 0,5024 e um pose loss de 0,4766. Para fins de comparação, na época 1 o box loss era de 1,828 e o pose loss era de 10,57. Olhando para os keypoints que o modelo gerou para as imagens de validação, percebe-se a olho nu que eles parecem fazer sentido, apesar de ainda te rmuito espaço a melhorar. O notebook apresenta uma análise mais aprofundada e gráficos relativos a evolução das métricas ao longo das épocas.