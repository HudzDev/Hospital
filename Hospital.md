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
{   "nome": "Dr. Murilo Coelho",
    "data_nascimento": "2006-04-10",
    "especialidades": [
        "Ginecologisca"
    ],
    "tipo": "Especialista",
    "contato": { 
        "telefone": "999999991",
        "email": "murilo@hospital.com"
    },
    "status": 1,
    "documentos": { 
        "CPF": "10101010101", 
        "CRM": "SP000001"
    }
},
{
    "nome": "Dr. Matheus Oliveira",
    "data_nascimento": "2006-05-11",
    "especialidades": [
        "Clinica Geral"
    ],
    "tipo": "Especialista",
    "contato": { 
        "telefone": "999999992",
        "email": "matheus@hospital.com"
    },
    "status": 1,
    "documentos": { 
        "CPF": "10101010102", 
        "CRM": "SP000002"
    }
},
{
    "nome": "Dr. Kauan Lusbel",
    "data_nascimento": "2003-05-15",
    "especialidades": [
        "Dermatologia"
    ],
    "tipo": "Especialista",
    "contato": { 
        "telefone": "999999993",
        "email": "lusbel@hospital.com"
    },
    "status": 1,
    "documentos": { 
        "CPF": "10101010103", 
        "CRM": "SP000003"
    }
},
{
    "nome": "Dr. Maykon Silva",
    "data_nascimento": "",
    "especialidades": [
        "Gastrenterologia"
    ],
    "tipo": "Especialista",
    "contato": { 
        "telefone": "999999994",
        "email": "maykon@hospital.com"
    },
    "status": 1,
    "documentos": { 
        "CPF": "10101010104", 
        "CRM": "SP000004"
    }
},
{
    "nome": "Dra. Andressa Prudente",
    "data_nascimento": "",
    "especialidades": [
        "Pediatria"
    ],
    "tipo": "Especialista",
    "contato": { 
        "telefone": "999999995",
        "email": "andressa@hospital.com"
    },
    "status": 1,
    "documentos": { 
        "CPF": "10101010105", 
        "CRM": "SP000005"
    }
},
{
    "nome": "Dra. Anna Cristina",
    "data_nascimento": "",
    "especialidades": [
        "Pediatria"
    ],
    "tipo": "Especialista",
    "contato": { 
        "telefone": "999999996",
        "email": "anna@hospital.com"
    },
    "status": 1,
    "documentos": { 
        "CPF": "10101010106", 
        "CRM": "SP000006"
    }
},
{
    "nome": "Dr. Hudson de Souza",
    "data_nascimento": "2003-11-09",
    "especialidades": [
        "Cirurgiao Geral"
    ],
    "tipo": "Especialista",
    "contato": { 
        "telefone": "999999997",
        "email": "hudson@hospital.com"
    },
    "status": 1,
    "documentos": { 
        "CPF": "10101010107", 
        "CRM": "SP000007"
    }
},
{
    "nome": "Dr. Victor de Curtis",
    "data_nascimento": "",
    "especialidades": [
        "Ortopedia"
    ],
    "tipo": "Especialista",
    "contato": { 
        "telefone": "999999998",
        "email": "curtis@hospital.com"
    },
    "status": 1,
    "documentos": { 
        "CPF": "10101010108", 
        "CRM": "SP000008"
    }
},
{
    "nome": "Gabriel Augusto",
    "data_nascimento": "",
    "especialidades": [
        "Neurologia"
    ],
    "tipo": "Especialista",
    "contato": { 
        "telefone": "999999999",
        "email": "curtis@hospital.com"
    },
    "status": 1,
    "documentos": { 
        "CPF": "10101010109", 
        "CRM": "SP000009"
    }
},
{
    "nome": "Dra. Aurora Seles",
    "data_nascimento": "",
    "especialidades": [
        "Psiquiatria"
    ],
    "tipo": "Especialista",
    "contato": { 
        "telefone": "999999990",
        "email": "curtis@hospital.com"
    },
    "status": 1,
    "documentos": { 
        "CPF": "10101010100", 
        "CRM": "SP000000"
    }
} ]) </pre>
