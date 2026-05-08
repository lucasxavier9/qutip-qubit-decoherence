# Decoerência de Qubits sob a Equação de Lindblad: Simulação Numérica e Roteiro Didático com QuTiP


Este repositório apresenta uma implementação numérica da equação mestra de Lindblad aplicada a qubits, utilizando a biblioteca QuTiP (Quantum Toolbox in Python). O projeto investiga os efeitos de relaxação e desfasamento em sistemas quânticos abertos, com foco na análise de decoerência, fidelidade, pureza e tempo de coerência transversal \(T_2\).

O trabalho foi desenvolvido no contexto de estudos em computação quântica e sistemas quânticos abertos, servindo também como ferramenta educacional para o ensino de dinâmica de qubits e equações mestras.

---

# Objetivos

- Simular a dinâmica de um qubit aberto utilizando a equação de Lindblad.
- Investigar os efeitos de relaxação de energia e desfasamento puro.
- Estimar numericamente o tempo de coerência transversal \(T_2\).
- Comparar resultados numéricos com previsões teóricas.
- Explorar aspectos numéricos como convergência temporal e estabilidade.
- Disponibilizar um ambiente reproduzível para estudos e ensino de sistemas quânticos abertos.

---

# Fundamentação Física

A evolução de sistemas quânticos abertos é descrita pela equação mestra de Lindblad:

$$
\frac{d\rho}{dt} = -\frac{i}{\hbar}[H,\rho] + \sum_k \left(
L_k \rho L_k^\dagger - \frac{1}{2}\{L_k^\dagger L_k, \rho\}
\right)
$$

onde:

- \(\rho\) é a matriz densidade;
- \(H\) é o Hamiltoniano do sistema;
- \(L_k\) são os operadores de Lindblad associados aos canais dissipativos.

O modelo implementado considera:

- Relaxação de energia (amplitude damping);
- Desfasamento puro (pure dephasing).

---

# Tecnologias Utilizadas

- Python 3.9
- QuTiP 5.0
- NumPy
- SciPy
- Matplotlib
- Pandas
- Seaborn
- Jupyter Notebook

---

# Principais Funcionalidades

## Simulação da Equação de Lindblad

Integração temporal da dinâmica de um qubit aberto utilizando o solver `mesolve()` do QuTiP.

## Análise de Decoerência

Estudo dos efeitos de:

- Relaxação longitudinal \(T_1\);
- Desfasamento transversal \(T_2\);
- Fidelidade quântica;
- Pureza da matriz densidade;
- Evolução do vetor de Bloch.

## Estimativa Numérica de \(T_2\)

O tempo de coerência transversal é estimado a partir do ajuste exponencial sobre:

$$
|\rho_{01}(t)|
$$

com extração de:

- valor ajustado de T₂;
- incerteza ±1σ;
- coeficiente de determinação R².

## Convergência Temporal

Avaliação do impacto do passo temporal e da discretização sobre a precisão numérica das simulações.

## Mapas Paramétricos

Geração de mapas de calor para:

- tempo de coerência \(T_2\);
- pureza final;
- regimes de decoerência.

# Resultados Obtidos

O projeto reproduz numericamente diversos comportamentos previstos teoricamente:

- Decaimento exponencial da coerência;
- Redução da fidelidade sob ruído;
- Evolução para estados mistos;
- Concordância entre valores numéricos e teóricos de \(T_2\);
- Influência direta das taxas \(\gamma_1\) e \(\gamma_\phi\) nos tempos de decoerência.

---

# Como Executar

## 1. Clone o repositório

```bash
git clone https://github.com/lucasxavier9/qutip-qubit-decoherence
cd qutip-qubit-decoherence
```

---

## 2. Instale as dependências

```bash
pip install qutip numpy scipy matplotlib seaborn pandas

```

---

## 3. Execute o notebook

```bash
jupyter notebook analise_decoerencia_.ipynb
```

## 4. Execute todas as células em ordem
Os resultados serão salvos automaticamente em:
```
results/
├── figures/     
├── tables/        
├── summary.csv 
└── all_results.pkl
```
---

# Exemplos de Análises

O notebook inclui:

- Evolução temporal da fidelidade;
- Evolução da pureza;
- Componentes do vetor de Bloch;
- Ajuste exponencial de \(T_2\);
- Análise de convergência temporal;
- Comparação entre teoria e simulação;
- Heatmaps de decoerência.

---

# Artigo Científico

O código deste repositório acompanha o artigo:

## Decoerência de Qubits sob a Equação de Lindblad: Simulação Numérica e Roteiro Didático com QuTiP

O trabalho apresenta:

- Fundamentação teórica;
- Metodologia numérica;
- Validação de \(T_2\);
- Análise de convergência;
- Discussão pedagógica do uso do QuTiP.

---

# Autores

**Allan Miqueias de C. Santos** 

**Francisco de Assis Brito Filho** 

**Wedryson Lucas Xavier O. Souza** 

Universidade Federal Rural do Semi-Árido (UFERSA)  

Programa de Pós-Graduação em Engenharia Elétrica

