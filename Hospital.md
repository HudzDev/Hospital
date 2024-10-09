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
