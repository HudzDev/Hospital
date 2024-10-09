# Hospital
## Um hospital local precisa desenvolver um sistema para gerenciar seus dados clínicos e substituir planilhas e arquivos antigos por um banco de dados funcional. O objetivo é criar uma estrutura que registre médicos, pacientes, consultas, convênios, receitas médicas e muito mais...  

Considere a seguinte descrição:

No hospital, as internações têm sido registradas por meio de formulários eletrônicos que gravam os dados em arquivos. 

Para cada internação, são anotadas a data de entrada, a data prevista de alta e a data efetiva de alta, além da descrição textual dos procedimentos a serem realizados. 

As internações precisam ser vinculadas a quartos, com a numeração e o tipo. 

Cada tipo de quarto tem sua descrição e o seu valor diário (a princípio, o hospital trabalha com apartamentos, quartos duplos e enfermaria).

Também é necessário controlar quais profissionais de enfermaria estarão responsáveis por acompanhar o paciente durante sua internação. Para cada enfermeiro(a), é necessário nome, CPF e registro no conselho de enfermagem (COREN).

A internação, obviamente, é vinculada a um paciente – que pode se internar mais de uma vez no hospital – e a um único médico responsável.

<pre>db.internacoes.updateOne(
{ _id: ObjectId('6706bc56a4dd24a2e812f461') },
{ $set: { 
  quarto: { 
  id: ObjectId("66e996237cac832beb827a6a"),
  numero: "101",
  tipo: "Apartamento",
  valor_diario: 300 },
  enfermeiros_responsaveis: [ 
{ nome: "José Santos", cpf: "0376432100", registro: "CRE03764" },
{ nome: "Pedro Alves", cpf: "88297432100", registro: "CRE88297" } ]}
})</pre>

<pre>db.internacoes.updateOne(
{ _id: ObjectId('6706c570eeee5679bc5450a2') },
{ $set: { 
  quarto: { 
  id: ObjectId("66e996237cac832beb827a6b"),
  numero: "102",
  tipo: "Quarto Duplo",
  valor_diario: 200 },
  enfermeiros_responsaveis: [ 
{ nome: "Paula Lima", cpf: "12345678909", registro: "CRE12345" },
{ nome: "João Mendes", cpf: "98765432100", registro: "CRE67890" } ]}
})</pre>

Inclua ao menos dez médicos de diferentes especialidades.

Ao menos sete especialidades (considere a afirmação de que “entre as especialidades há pediatria, clínica geral, gastrenterologia e dermatologia”).

<pre>db.medicos.insertMany([
{ "nome": "Dr. Murilo Coelho",
  "data_nascimento": "2006-04-10",
  "especialidades": [
  "Ginecologisca" ],
  "tipo": "Especialista",
  "contato": { 
  "telefone": "999999991",
  "email": "murilo@hospital.com"
},
  "status": 1,
  "documentos": { 
  "CPF": "10101010101", 
  "CRM": "SP000001" }
},

{ "nome": "Dr. Matheus Oliveira",
  "data_nascimento": "2006-05-11",
  "especialidades": [
  "Clinica Geral" ],
  "tipo": "Especialista",
  "contato": { 
  "telefone": "999999992",
  "email": "matheus@hospital.com"
},
  "status": 1,
  "documentos": { 
  "CPF": "10101010102", 
  "CRM": "SP000002" }
},

{ "nome": "Dr. Kauan Lusbel",
  "data_nascimento": "2003-05-15",
  "especialidades": [
  "Dermatologia" ],
  "tipo": "Especialista",
  "contato": { 
  "telefone": "999999993",
  "email": "lusbel@hospital.com"
},
  "status": 1,
  "documentos": { 
  "CPF": "10101010103", 
  "CRM": "SP000003" }
},

{ "nome": "Dr. Maykon Silva",
  "data_nascimento": "",
  "especialidades": [
  "Gastrenterologia" ],
  "tipo": "Especialista",
  "contato": { 
  "telefone": "999999994",
  "email": "maykon@hospital.com"
},
  "status": 1,
  "documentos": { 
  "CPF": "10101010104", 
  "CRM": "SP000004" }
},

{ "nome": "Dra. Andressa Prudente",
  "data_nascimento": "",
  "especialidades": [
  "Pediatria" ],
  "tipo": "Especialista",
  "contato": { 
  "telefone": "999999995",
  "email": "andressa@hospital.com"
},
  "status": 1,
  "documentos": { 
  "CPF": "10101010105", 
  "CRM": "SP000005" }
},

{ "nome": "Dra. Anna Cristina",
  "data_nascimento": "",
  "especialidades": [
  "Pediatria" ],
  "tipo": "Especialista",
  "contato": { 
  "telefone": "999999996",
  "email": "anna@hospital.com"
},
  "status": 1,
  "documentos": { 
  "CPF": "10101010106", 
  "CRM": "SP000006" }
},

{ "nome": "Dr. Hudson de Souza",
  "data_nascimento": "2003-11-09",
  "especialidades": [
  "Cirurgiao Geral" ],
  "tipo": "Especialista",
  "contato": { 
  "telefone": "999999997",
  "email": "hudson@hospital.com"
},
  "status": 1,
  "documentos": { 
  "CPF": "10101010107", 
  "CRM": "SP000007" }
},

{ "nome": "Dr. Victor de Curtis",
  "data_nascimento": "",
  "especialidades": [
  "Ortopedia" ],
  "tipo": "Especialista",
  "contato": { 
  "telefone": "999999998",
  "email": "curtis@hospital.com"
},
  "status": 1,
  "documentos": { 
  "CPF": "10101010108", 
  "CRM": "SP000008" }
},

{ "nome": "Gabriel Augusto",
  "data_nascimento": "",
  "especialidades": [
  "Neurologia" ],
  "tipo": "Especialista",
  "contato": { 
  "telefone": "999999999",
  "email": "curtis@hospital.com"
},
  "status": 1,
  "documentos": { 
  "CPF": "10101010109", 
  "CRM": "SP000009" }
},

{ "nome": "Dra. Aurora Seles",
  "data_nascimento": "",
  "especialidades": [
  "Psiquiatria" ],
  "tipo": "Especialista",
  "contato": { 
  "telefone": "999999990",
  "email": "curtis@hospital.com"
},
  "status": 1,
  "documentos": { 
  "CPF": "10101010100", 
  "CRM": "SP000000" }
} ]) </pre>

Inclua ao menos 15 pacientes.

<pre>db.pacientes.insertMany([
{ "nome": "Joséfa Almeida",
  "data_nascimento": "1950-06-03",
  "endereco": {
  "logradouro": "Rua C",
  "numero": "44",
  "bairro": "Vila Mariana",
  "cidade": "São Paulo",
  "estado": "SP",
  "CEP": "12345675" 
},
  "contato": {
  "telefone": "222233344444",
  "email": "josefa@gmail.com" 
},
  "documentos": {
  "CPF": "87654321658",
  "RG": "SP123248" 
},
  "convenio": {
  "nome": "Unimed",
  "validade": "2021-12-31",
  "CNPJ": "12345678000101",
  "carencia": 30 }
},

{ "nome": "João Silva",
  "data_nascimento": "1990-05-15",
  "endereco": {
  "logradouro": "Avenida A",
  "numero": "50",
  "bairro": "Centro",
  "cidade": "São Paulo",
  "estado": "SP",
  "CEP": "98765432"
},
  "contato": {
  "telefone": "111122223333",
  "email": "joao@gmail.com"
},
  "documentos": {
  "CPF": "12345678901",
  "RG": "SP123458"
},
  "convenio": {
  "nome": "Bradesco Saúde",
  "validade": "2023-05-30",
  "CNPJ": "12345678000102",
  "carencia": 60 }
},
   
{ "nome": "Ana Souza",
  "data_nascimento": "1985-03-22",
  "endereco": {
  "logradouro": "Rua C",
  "numero": "15",
  "bairro": "Jardim Paulista",
  "cidade": "São Paulo",
  "estado": "SP",
  "CEP": "23456789"
},
  "contato": {
  "telefone": "444455556666",
  "email": "ana@gmail.com"
},
  "documentos": {
  "CPF": "23456789012",
  "RG": "SP123459"
},
  "convenio": {
  "nome": "Amil",
  "validade": "2022-11-20",
  "CNPJ": "12345678000103",
  "carencia": 45 }
},
    
{ "nome": "Lucas Pereira",
  "data_nascimento": "1995-07-10",
  "endereco": {
  "logradouro": "Rua D",
  "numero": "8",
  "bairro": "Vila Mariana",
  "cidade": "São Paulo",
  "estado": "SP",
  "CEP": "34567890"
},
  "contato": {
  "telefone": "555566667777",
  "email": "lucas@gmail.com"
},
  "documentos": {
  "CPF": "34567890123",
  "RG": "SP123460"
},
  "convenio": {
  "nome": "SulAmérica",
  "validade": "2023-06-15",
  "CNPJ": "12345678000104",
  "carencia": 90 }
},
    
{ "nome": "Fernanda Costa",
  "data_nascimento": "1992-09-25",
  "endereco": {
  "logradouro": "Rua E",
  "numero": "35",
  "bairro": "Morumbi",
  "cidade": "São Paulo",
  "estado": "SP",
  "CEP": "45678901"
},
  "contato": {
  "telefone": "888899990000",
  "email": "fernanda@gmail.com"
},
  "documentos": {
  "CPF": "45678901234",
  "RG": "SP123461"
},
  "convenio": {
  "nome": "Porto Seguro",
  "validade": "2024-03-12",
  "CNPJ": "12345678000105",
  "carencia": 30 }
},
    
{ "nome": "Carlos Almeida",
  "data_nascimento": "1988-12-05",
  "endereco": {
  "logradouro": "Rua F",
  "numero": "60",
  "bairro": "Itaim Bibi",
  "cidade": "São Paulo",
  "estado": "SP",
    "CEP": "56789012"
},
  "contato": {
  "telefone": "999900001111",
  "email": "carlos@gmail.com"
},
  "documentos": {
  "CPF": "56789012345",
  "RG": "SP123462"
},
  "convenio": {
  "nome": "Intermedica",
  "validade": "2022-07-19",
  "CNPJ": "12345678000106",
  "carencia": 15 }
},
    
{ "nome": "Patrícia Lima",
  "data_nascimento": "1993-01-14",
  "endereco": {
  "logradouro": "Rua G",
  "numero": "72",
  "bairro": "Bela Vista",
  "cidade": "São Paulo",
  "estado": "SP",
  "CEP": "67890123"
},
  "contato": {
  "telefone": "333344445555",
  "email": "patricia@gmail.com"
},
  "documentos": {
  "CPF": "67890123456",
  "RG": "SP123463"
},
  "convenio": {
  "nome": "São Cristóvão",
  "validade": "2024-09-30",
  "CNPJ": "12345678000107",
  "carencia": 60 }
},
    
{ "nome": "Renato Ferreira",
  "data_nascimento": "1989-04-17",
  "endereco": {
  "logradouro": "Rua H",
  "numero": "22",
  "bairro": "Jardim Europa",
  "cidade": "São Paulo",
  "estado": "SP",
  "CEP": "78901234"
},
  "contato": {
  "telefone": "222233334444",
  "email": "renato@gmail.com"
},
  "documentos": {
  "CPF": "78901234567",
  "RG": "SP123464"
},
  "convenio": {
  "nome": "Golden Cross",
  "validade": "2022-10-05",
  "CNPJ": "12345678000108",
  "carencia": 30 }
},
    
{ "nome": "Sofia Mendes",
  "data_nascimento": "1991-02-29",
  "endereco": {
  "logradouro": "Rua I",
  "numero": "90",
  "bairro": "Santa Cecília",
  "cidade": "São Paulo",
  "estado": "SP",
  "CEP": "89012345"
},
  "contato": {
  "telefone": "666677778888",
  "email": "sofia@gmail.com"
},
  "documentos": {
  "CPF": "89012345678",
  "RG": "SP123465"
},
  "convenio": {
  "nome": "Unimed",
  "validade": "2025-01-01",
  "CNPJ": "12345678000109",
  "carencia": 45 }
},

{ "nome": "Eduardo Santos",
  "data_nascimento": "1986-08-08",
  "endereco": {
  "logradouro": "Rua J",
  "numero": "5",
  "bairro": "Vila Madalena",
  "cidade": "São Paulo",
  "estado": "SP",
  "CEP": "90123456"
},
  "contato": {
  "telefone": "444455559999",
  "email": "eduardo@gmail.com"
},
  "documentos": {
  "CPF": "90123456789",
  "RG": "SP123466"
},
  "convenio": {
  "nome": "Bradesco Saúde",
  "validade": "2024-04-20",
  "CNPJ": "12345678000110",
  "carencia": 30 }
},
    
{ "nome": "Clara Rocha",
  "data_nascimento": "1994-06-18",
  "endereco": {
  "logradouro": "Rua K",
  "numero": "11",
  "bairro": "Pinheiros",
  "cidade": "São Paulo",
  "estado": "SP",
  "CEP": "01234567"
},
  "contato": {
  "telefone": "111122224444",
  "email": "clara@gmail.com"
},
  "documentos": {
  "CPF": "01234567890",
  "RG": "SP123467"
},
  "convenio": {
  "nome": "Amil",
  "validade": "2022-05-15",
  "CNPJ": "12345678000111",
  "carencia": 60 }
},
    
{ "nome": "Fábio Gomes",
  "data_nascimento": "1990-12-10",
  "endereco": {
  "logradouro": "Rua L",
  "numero": "30",
  "bairro": "Liberdade",
  "cidade": "São Paulo",
  "estado": "SP",
  "CEP": "23456780"
},
  "contato": {
  "telefone": "222233334444",
  "email": "fabio@gmail.com"
},
  "documentos": {
  "CPF": "12345678901",
  "RG": "SP123468"
},
  "convenio": {
  "nome": "SulAmérica",
  "validade": "2023-09-30",
  "CNPJ": "12345678000112",
  "carencia": 90 }
},
    
{ "nome": "Lívia Martins",
  "data_nascimento": "1993-10-03",
  "endereco": {
  "logradouro": "Rua M",
  "numero": "44",
  "bairro": "Alto de Pinheiros",
  "cidade": "São Paulo",
  "estado": "SP",
  "CEP": "34567890"
},
  "contato": {
  "telefone": "888899990000",
  "email": "livia@gmail.com"
},
  "documentos": {
  "CPF": "23456789012",
  "RG": "SP123469"
},
  "convenio": {
  "nome": "Porto Seguro",
  "validade": "2025-11-30",
  "CNPJ": "12345678000113",
  "carencia": 15 }
},
    
{ "nome": "Gustavo Torres",
  "data_nascimento": "1984-11-22",
  "endereco": {
  "logradouro": "Rua N",
  "numero": "28",
  "bairro": "Campo Belo",
  "cidade": "São Paulo",
  "estado": "SP",
  "CEP": "54321678"
},
  "contato": {
  "telefone": "999988887777",
  "email": "gustavo@gmail.com"
},
  "documentos": {
  "CPF": "34567890123",
  "RG": "SP123470"
},
  "convenio": {
  "nome": "Amil",
  "validade": "2024-07-30",
  "CNPJ": "12345678000114",
  "carencia": 30 }
},
    
{ "nome": "Juliana Lima",
  "data_nascimento": "1996-03-19",
  "endereco": {
  "logradouro": "Avenida N",
  "numero": "75",
  "bairro": "Vila Clementino",
  "cidade": "São Paulo",
  "estado": "SP",
  "CEP": "67890123"
 },
  "contato": {
  "telefone": "777788889999",
  "email": "juliana@gmail.com"
},
  "documentos": {
  "CPF": "45678901234",
  "RG": "SP123471"
},
  "convenio": {
  "nome": "Intermedica",
  "validade": "2023-08-15",
  "CNPJ": "12345678000115",
  "carencia": 15 }
} ])</pre>
