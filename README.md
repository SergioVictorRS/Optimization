
---
# Agendador de Reuniões com OptaPlanner

Este projeto é uma **adaptação personalizada** do exemplo de agendamento de reuniões do [OptaPlanner](https://www.optaplanner.org/) para funcionar com arquivos Excel fornecidos.

Ele utiliza algoritmos de otimização para alocar reuniões de forma eficiente, respeitando restrições como disponibilidade, salas e conflitos de agenda.

---

## Requisitos

- Java 11 ou superior
- Maven 3.6 ou superior
- IDE com suporte a Java (eg. Eclipse)

---

## Como Executar Localmente
````markdown
### 1. Clone o Repositório

```bash
git clone https://github.com/SergioVictorRS/Optimization.git
cd seu-repositorio
````

### 2. Insira o Arquivo Excel

Coloque o arquivo `.xlsx` com os dados da empresa na pasta:

```
data/unsolved/
```

> O formato do arquivo deve seguir o padrão esperado pelo código `MeetingSchedulingXlsxFileIO.java`.
> Caso necessário, ajuste esse leitor para se adaptar aos dados da planilha
### 3. Compile o Projeto

```bash
mvn clean install
```

### 4. Execute a Aplicação

```bash
mvn exec:java -Dexec.mainClass="org.optaplanner.examples.meetingscheduling.app.MeetingSchedulingApp"
```

Ao executar, será aberta uma **interface gráfica (GUI)** onde você poderá visualizar e acompanhar a solução em tempo real.

---

## Como Funciona

O OptaPlanner resolve o problema de agendamento usando inteligência artificial (heurísticas e metaheurísticas), considerando:

* Disponibilidade de participantes
* Restrições de horário
* Capacidade das salas
* Conflitos entre reuniões
* Preferências de alocação

Você pode alterar os critérios do projeto em:

```
src/main/java/org/optaplanner/examples/meetingscheduling/solver/MeetingSchedulingConstraintProvider.java
```

---

## Estrutura do Projeto

```
├── src/
│   └── main/
│       ├── java/
│           └── org/optaplanner/examples/meetingscheduling/
│       
├── data/
│   └── unsolved/
│   |   └── arquivo.xlsx
│   └── solved/
│       └── arquivo.xlsx
├── pom.xml
└── README.md
```

---

## Personalização

* **Entrada personalizada:** Edite `MeetingSchedulingXlsxFileIO.java` para aceitar novas colunas ou formatos do Excel.
* **Restrições de negócios:** Ajuste o `ConstraintProvider` para refletir regras da empresa.
* **Configuração do solver:** Modifique `meetingSchedulingSolverConfig.xml` para mudar o algoritmo ou tempo de execução.

---

---
Este projeto é baseado no OptaPlanner, que é licenciado sob a [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0).
