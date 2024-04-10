# Desafio-CRUD- Agenda de contatos


Este projeto consiste em uma aplicação web simples para gerenciar uma agenda de contatos, permitindo a realização das operações 
  **CRUD (Create, Read, Update, Delete)** em uma lista de contatos.

### Funcionalidades
A aplicação oferece as seguintes funcionalidades:


* **Cadastro de Pessoa:**
Adicionar novos contatos informando nome, número de telefone e email.
*  **Listagem de Pessoas:** 
Exibir a lista de contatos cadastrados.
*  **Atualização de Pessoas:**
Atualizar informações de um contato existente, como email ou número de telefone.
*  **Exclusão de Pessoas:**
Remover um contato da agenda.
*  **Sair do Menu:**
Encerrar a execução da aplicação.

 ### **Como Usar**
Para utilizar a aplicação, basta seguir estes passos:
Abra o arquivo html em um navegador web.
Ao abrir a aplicação, um menu será exibido com as opções disponíveis.
Escolha a opção desejada digitando o número correspondente.
Siga as instruções para cada operação conforme solicitado.

**Detalhes da Implementação**
~~~js
Copy code
let arryAgenda=[]
~~~
~~~js
function Menu() {
    return parseInt(prompt(`cadastrando telefone e email ao seus contatos
    1- Cadastro Pessoa
    2- Pessoas Agenda
    3- Atualizar Pessoas
    4- Deletar pessoas
    5- sair do menu
    `));
}
~~~
O código JavaScript acima define a **função Menu()** que exibe um menu de opções para o usuário, permitindo escolher entre as diferentes operações disponíveis.

~~~js
Copy code
function AddPessoa() {
    const nomeContato= prompt("Digitar nome do novo contato");
    const numeroContato= prompt("Digitar número do novo contato");
    const emailContato= prompt("Digitar email do cantato");
    const dataAtual = new Date().toLocaleDateString();
    
    arryAgenda.push({nomeContato,numeroContato,emailContato,dataAtual});

    console.log(arryAgenda);
}
~~~
A **função AddPessoa()** é responsável por adicionar um novo contato à agenda, solicitando ao usuário que insira o nome, número de telefone e email do contato.

~~~js
Copy code
const ListPessoa = () => {
    let listPessoa = "";
    arryAgenda.forEach((dataUser) =>{
        listPessoa += `
        Nome: ${dataUser.nomeContato}, Telefone: ${dataUser.numeroContato}, Email: ${dataUser.emailContato}, Data: ${dataUser.dataAtual}`;
    });

    console.log(listPessoa);
    alert("*****Lista de usuários*****" + listPessoa);
}
~~~
A **função ListPessoa()**  lista todos os contatos cadastrados na agenda, exibindo seus nomes, números de telefone, emails e datas de cadastro.

~~~js 
Copy code
function UpdatePessoas() {
    let  atualizarDados =parseInt(prompt(`qual das opçoes você deseja atualizar
    1-E-mail
    2-Telefone
    3- Voltar para o menu anterior`));
let atualizarContatos = true;
while (atualizarContatos) {
    switch (atualizarDados) {
        // Casos para atualizar email ou telefone...
    }
} 
}
~~~
A **função UpdatePessoas()** permite ao usuário atualizar as informações de um contato existente na agenda, como email ou número de telefone.

~~~js
Copy code
function DeleteContato() {
    const emailDelete = prompt("Informe o email para realizar o delete!")
    const indiceDelete = arryAgenda.findIndex(email => email.emailContato === emailDelete)

    const confirmacao = window.confirm(`Você deseja mesmo excluir o usuário ${emailDelete}`)
    
    if (confirmacao) {
        arryAgenda.splice(indiceDelete, 1)
    }

    alert("Usuário deletado com sucesso!")
}
~~~
Por fim, a **função DeleteContato()** permite excluir um contato da agenda, solicitando ao usuário que informe o email do contato a ser removido.
~~~js
Copy code
 function DeleteContato() {
        const emailDelete = prompt("Informe o email para deletar o contato!")
        const indiceDelete = arryAgenda.findIndex(email => email.emailContato === emailDelete)

        const confirmacao = window.confirm(`Você deseja mesmo excluir o contato ${emailDelete}`)
        

        if (confirmacao) {
            arryAgenda.splice(indiceDelete, 1)
        }

        alert("Usuário deletado com sucesso!")
      }
~~~
