# HackatonFiap5
Desafio Final da PósTech em IA para Devs da FIAP - Projeto de Reconhecimento Visual com IA de objetos cortantes

# 🔪 VisionGuard: Detecção de Objetos Cortantes com YOLOv8

Este repositório apresenta o **VisionGuard**, um MVP de sistema inteligente que detecta **objetos cortantes (facas, tesouras, armas, etc.)** em vídeos de segurança. Desenvolvido como parte do **Hackathon FIAP5**, o projeto utiliza **YOLOv8**, **Roboflow**, **OpenCV** e **alertas por e-mail**.

---

## 🎯 Objetivo

Criar uma pipeline funcional para:

- ✅ Treinar modelo YOLOv8 com dataset anotado.
- ✅ Detectar objetos perigosos em vídeos.
- ✅ Salvar frames com detecção.
- ✅ Enviar alertas automáticos por **e-mail com imagem**.
- ✅ Documentar o processo com código reprodutível (Colab + GitHub).

---

## 🧠 Etapas do Projeto

| Etapa | Nome                              | Ferramentas                            | Resultado Esperado                          |
|-------|-----------------------------------|----------------------------------------|---------------------------------------------|
| 1     | Setup do ambiente                 | Google Colab, GitHub                   | Ambiente funcional com dependências         |
| 2     | Preparação do Dataset             | Roboflow                               | Dataset com classes `knife`, `scissors`, 'cutter',  etc. |
| 3     | Treinamento do Modelo             | YOLOv8 (Ultralytics)                   | Modelo `.pt` treinado                       |
| 4     | Detecção em vídeo                 | OpenCV, YOLOv8                         | Bounding boxes + prints                     |
| 5     | Sistema de Alerta por E-mail      | `smtplib`, Gmail                       | E-mail com imagem enviada em tempo real     |
| 6     | Documentação e Deploy             | Colab, Markdown                        | Repositório com README e notebook final     |

---

## 📁 Dataset (via Roboflow)

Utilizamos o [Roboflow](https://roboflow.com) para:

- Anotar manualmente imagens com objetos cortantes
- Dividir entre treino, validação e teste
- Exportar para YOLOv8
- Fazer correção e unificação de classes (`knife`, `knives` → `knife`, etc.)

Exemplo de estrutura exportada:

cortantesMVP-2/ ├── train/ ├── valid/ ├── test/ ├── data.yaml

## 📨 Alerta por E-mail

- Sempre que um objeto cortante é detectado, um e-mail com a imagem é enviado automaticamente.
- Sistema previne flood: até 10 alertas por minuto.

```python
def send_alert(frame, class_name, confidence):
    # Salva o frame
    # Envia e-mail com imagem + descrição
```

## 🎥 Processo de Inferência

- O vídeo é analisado frame a frame.
- Cada detecção com confiança > 60% aciona o alerta.
- O vídeo final com bounding boxes é salvo.

## 📁 Estrutura dos Arquivos

```
Hackaton_FIAP5/
├── data.yaml
├── video.mp4
├── runs/
│   └── detect/
│       └── train4/
│           └── weights/best.pt
├── inferencia_com_alerta.py
└── alertas/
    ├── alerta_YYYYMMDD_HHMM.jpg
    └── video_processado.mp4
```

## 📊 Resultados

- `knife`: mAP@50 = 0.639
- `cutter`: mAP@50 = 0.916
- `sickle`: mAP@50 = 0.994
- `precision`: 0.877
- `recall`: 0.839

## ✅ Conclusão

O modelo YOLOv8 mostrou-se eficaz para detecção de objetos cortantes em ambiente de vídeo. O envio automatizado de alertas amplia a utilidade do sistema para aplicações em segurança e vigilância.

---

Criado com 💡 no Hackaton FIAP - Fase 5 por Beatriz Cardoso Cunha em 21 de abril de 2025

🔗LINKS DO PROJETO
- Link para Video Explicativo: https://youtu.be/fLekEP_65k0 
- Link para Video processado de validação do MVP: https://youtu.be/yKj2Do8kJNk
- Link para o Projeto Google Drive: https://drive.google.com/drive/folders/1J91UZkjRoVw3EFS0sz1kHlMbcLtbM0fc?usp=sharing
- Link do Projeto no RoboFlow: https://app.roboflow.com/join/eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ3b3Jrc3BhY2VJZCI6InAwd0JlZ05UbFlVdjB4VUtkajV3ajVXZkxXdjIiLCJyb2xlIjoib3duZXIiLCJpbnZpdGVyIjoiZmlhcGJlYUBnbWFpbC5jb20iLCJpYXQiOjE3NDUyNjEzODh9.e_nJEFZ7bQKkRzifFSkOEsfTPGD3VmFYZ2O7Z8pP2Oc 
- OBS: o vídeo 2 está anexado no Github


