# 🏭 Sistema de Monitoramento de Energia Fabril

![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557c?style=for-the-badge&logo=python&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-3776AB?style=for-the-badge&logo=python&logoColor=white)

Sistema inteligente para monitoramento e análise de consumo energético em máquinas industriais, com detecção automática de anomalias e geração de relatórios visuais.

## 📋 Descrição

Este sistema realiza o monitoramento contínuo do consumo energético de máquinas têxteis (Tear Jato e Rama de Acabamento), identificando padrões de consumo anormais e acionando alertas ou paradas preventivas quando necessário.

## ✨ Funcionalidades

- **Monitoramento em Tempo Real**: Análise linha por linha dos dados de consumo
- **Detecção Inteligente de Anomalias**: Sistema de alertas em dois níveis (Ideal e Crítico)
- **Parada Automática de Segurança**: Desligamento preventivo quando limite crítico é atingido
- **Visualização Gráfica**: Gráficos profissionais com zonas de segurança destacadas
- **Relatórios Detalhados**: Estatísticas completas por máquina e turno
- **Suporte Multi-Máquina**: Processamento simultâneo de múltiplas máquinas

## 🎯 Limites de Operação

### Tear Jato
- **Ideal**: < 50.0 kW
- **Crítico**: ≥ 65.0 kW

### Rama de Acabamento
- **Ideal**: < 135.0 kW
- **Crítico**: ≥ 155.0 kW

## 🔧 Tecnologias Utilizadas

- **Python 3.x**
- **Pandas**: Manipulação e análise de dados
- **NumPy**: Operações numéricas
- **Matplotlib**: Geração de gráficos
- **Seaborn**: Estilização visual

## 📦 Instalação

```bash
# Instale as dependências necessárias
pip install pandas numpy matplotlib seaborn
```

## 🚀 Como Usar

1. **Prepare o arquivo de dados**: Certifique-se de ter um arquivo CSV chamado `leituras_energia_fabrica.csv` com as seguintes colunas:
   - `data_hora`: Data e hora da leitura
   - `id_maquina`: Identificador da máquina
   - `consumo_kw`: Consumo em kW
   - `status_operacional`: Status da máquina (OPERANDO/PARADA)

2. **Execute o sistema**:
```bash
python monitor_energia.py
```

3. **Analise os resultados**: O sistema irá:
   - Processar cada máquina identificada no arquivo
   - Exibir alertas em tempo real no console
   - Gerar gráficos visuais de análise
   - Apresentar resumo estatístico completo

## 📊 Exemplo de Saída

```
===== TRATATIVA DE DADOS PARA EMPRESA AMJ'N =====

📂 LENDO OS ARQUIVOS: leituras_energia_fabrica.csv...
⚙️ MÁQUINAS ENCONTRADAS: ['Tear_Jato_01' 'Rama_Acabamento_02']

==================================================
✅ MONITOR INICIADO: 'Tear_Jato_01'
--> METAS: IDEAL < 50.0kW | CRÍTICO > 65.0kW

⚠️ ALERTA | Tear_Jato_01: 55.2kW (Acima da meta)
🛑 PERIGO | Tear_Jato_01 atingiu 66.8kW em 2024-01-15 14:30:00 -> PARADA ACIONADA!

📊 RESUMO DO TURNO: Tear_Jato_01
• OCORRÊNCIA ACIMA DA META: 12
• PICOS CRÍTICOS: 1
• 🛑 STATUS: MÁQUINA TERIA SIDO PARADA ÀS 14:30
```

## 📈 Interpretação dos Gráficos

Os gráficos gerados apresentam:

- **Zona Verde**: Consumo eficiente (abaixo do limite ideal)
- **Zona Amarela**: Zona de alerta (entre ideal e crítico)
- **Zona Vermelha**: Zona crítica (acima do limite crítico)
- **Linha Preta**: Consumo real ao longo do tempo
- **Pontos Laranja**: Momentos de alerta
- **Círculo Vermelho**: Ponto de parada (se houver)

## 🎨 Recursos Visuais

- Gráficos de alta qualidade com cores intuitivas
- Anotações automáticas em pontos críticos
- Formatação de eixos otimizada para leitura
- Legendas informativas e claras

## ⚠️ Tratamento de Erros

O sistema inclui tratamento robusto para:
- Arquivo CSV não encontrado
- Erros de formatação de dados
- Valores inconsistentes
- Exceções inesperadas

## 🔍 Estrutura do Código

```
MonitorEnergiaFabril (Classe Principal)
├── __init__(): Inicialização e configuração de limites
├── _verificar_seguranca(): Análise de segurança do consumo
├── processar_lote_pandas(): Processamento em lote dos dados
└── gerar_grafico_analise(): Geração de visualizações
```

## 📝 Formato do Arquivo CSV

```csv
data_hora,id_maquina,consumo_kw,status_operacional
2024-01-15 08:00:00,Tear_Jato_01,45.2,OPERANDO
2024-01-15 08:15:00,Tear_Jato_01,48.7,OPERANDO
2024-01-15 08:30:00,Rama_Acabamento_02,128.3,OPERANDO
```

## 🤝 Contribuindo

Sugestões e melhorias são bem-vindas! Sinta-se à vontade para:
- Reportar bugs
- Propor novas funcionalidades
- Melhorar a documentação

## 📄 Licença

Este projeto foi desenvolvido para a Empresa AMJ'N.

## 👥 Autores

Sistema de Monitoramento de Energia Fabril - Versão 1.0

---

**Desenvolvido com ❤️ para otimização energética industrial**
