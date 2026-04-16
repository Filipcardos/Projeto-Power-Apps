# 📱 App Power Apps – Taxímetros do Internato

Aplicativo desenvolvido em **Microsoft Power Apps** para apoiar o **envio, registro e consulta de taxímetros/atividades dos alunos do internato** em uma Instituição de Ensino Superior (IES).

Este projeto foi criado como uma **solução prática para um problema real**, utilizando conceitos de **Power Platform** e **Power Fx**.

---

## 🎯 Objetivo do Projeto

O objetivo do aplicativo é **digitalizar e centralizar** o processo de envio dos taxímetros do internato, facilitando:

- O registro das atividades pelos alunos  
- A organização das informações por período e módulo  
- A visualização e acompanhamento dos registros  

---

## 🛠️ Tecnologias Utilizadas

- **Microsoft Power Apps (Canvas App)**
- **Power Fx**
- **Power Platform**
- Fonte de dados: SharePoint / Lista interna *(estrutura adaptável)*

---

## 📋 Principais Funcionalidades

- ✅ Listagem dos registros enviados
- ✅ Busca dinâmica por título
- ✅ Ordenação alfabética (crescente/decrescente)
- ✅ Navegação entre telas (lista, detalhes e criação)
- ✅ Atualização manual dos dados
- ✅ Interface simples e intuitiva

---

## 🧠 Lógica do Aplicativo (Power Fx)

O aplicativo utiliza fórmulas **Power Fx** para controlar a lógica e o comportamento das telas, incluindo:

- `Filter()` → Filtrar registros conforme texto digitado  
- `SortByColumns()` → Ordenar registros dinamicamente  
- `StartsWith()` → Implementar busca por título  
- `UpdateContext()` → Controle de estado da ordenação  
- `Refresh()` → Atualização dos dados  
- `Navigate()` → Navegação entre telas  

### Exemplo de lógica utilizada:

```powerfx
SortByColumns(
    Filter(
        [@'Taxímetros - Internato'],
        StartsWith(Título, TextSearchBox1.Text)
    ),
    "Título",
    If(SortDescending1, SortOrder.Descending, SortOrder.Ascending)
)
``
