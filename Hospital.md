# Hospital

O objetivo é substituir suas planilhas antigas por um banco de dados moderno. Desenvolvendo uma estrutura completa que registra médicos, pacientes, consultas, convênios e receitas médicas. O sistema centraliza e organiza os dados, permitindo acesso e atualizações rápidas e seguras. Com isso, melhorando a eficiência do hospital, garantindo maior precisão no gerenciamento das informações clínicas.

## Estrutura

**Consultas**: Representa um atendimento realizado por um médico a um paciente.
* data
* id do médico
* id do paciente
* convênio
* valor
* diagnóstico
* receita

**Internações**: Representa o processo de admissão de um paciente para tratamento hospitalar.
* id do paciente
* id do médico
* datas
* procedimentos
* enfermeiros
* quarto

**Médicos**: Representa os médicos cadastrados no sistema.
* nome
* data de nascimento
* especialidades
* contatos
* documentos

**Enfermeiros**: Representa os enfermeiros cadastrados no sistema.
* nome
* documentos
