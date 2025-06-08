# 🧱 Programa CNC O0001 – Faceamento de Placa 200x100mm

Este repositório contém o código CNC do programa `O0001`, desenvolvido para **faceamento de uma placa metálica com dimensões 200mm x 100mm**, utilizando um **Centro de Usinagem com Controle Fanuc Oi-TD**.

---

## 🛠️ Especificações Técnicas

- **Peça**: Placa 200x100 mm  
- **Operação**: Faceamento da superfície superior  
- **Máquina**: Centro de Usinagem  
- **Controle CNC**: Fanuc Oi-TD  
- **Ferramenta**: Fresa de Facear Ø60mm (T01)  
- **Data da Programação**: 07/06/2025  
- **Sistema de Coordenadas**: G54  
- **Zero-Peça**: Canto inferior esquerdo da face superior  

---

## 🔧 Ferramenta Utilizada

| Ferramenta | Código | Tipo              | Diâmetro |
|------------|--------|-------------------|----------|
| T01        | M6     | Fresa de Facear   | 60 mm    |

---

## 🔍 Detalhes do Programa

### 1. Preparação e Segurança
- Seleção do plano XY (`G17`) e sistema métrico (`G21`)
- Coordenadas absolutas (`G90`)
- Cancelamento de compensação de raio (`G40`)
- Retração do eixo Z para segurança (`G53 G0 Z0 H0`)

### 2. Troca e Ativação da Ferramenta
- Seleção da ferramenta T01
- Troca física com `M6`
- Ativação do sistema de coordenadas da peça (`G54`)
- Rotação do spindle a 1500 RPM (`S1500 M3`)

### 3. Operação de Faceamento
- Aproximação até Z5 com compensação de altura (`G43 H1`)
- Mergulho até Z0 com avanço rápido e refrigeração (`M8`)
- Dois passes de faceamento completos alternando os eixos X e Y

### 4. Finalização
- Retração do Z para a posição de segurança da máquina
- Encerramento do programa com reset automático (`M30`)

---

## 📐 Comandos Relevantes

- `G17`: Seleção do plano de trabalho XY  
- `G21`: Programação em milímetros  
- `G90`: Coordenadas absolutas  
- `G40`: Cancelamento de compensação de raio  
- `G43 H1`: Compensação de altura da ferramenta  
- `G54`: Sistema de coordenadas da peça  
- `G53`: Movimentação em coordenadas da máquina  
- `M3`: Rotação do spindle no sentido horário  
- `M8` / `M30`: Liga a refrigeração / Encerra o programa  

---

## 🗂️ Arquivo Disponível

- [`O0001.nc`](O0001.nc): Código-fonte completo em G-Code para faceamento da placa.

---

## ✅ Observações

> Este programa é ideal para preparar a face inicial de placas metálicas retangulares. Comentários incluídos no código facilitam a leitura, manutenção e aprendizagem de usinagem CNC para centros de usinagem verticais.

---

## 📄 Licença

Este código-fonte é fornecido apenas para fins educacionais e técnicos. A aplicação em ambiente industrial deve seguir as normas de segurança e validação da sua empresa.
