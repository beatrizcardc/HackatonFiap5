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

Link para Video Explicativo: https://youtu.be/fLekEP_65k0 

