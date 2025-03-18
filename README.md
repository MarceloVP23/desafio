# desafio
// Array para armazenar os nomes
let listaDeNomes = [];

// Função para adicionar nomes à lista
function adicionarNome() {
    const input = document.getElementById("nome");
    const nome = input.value.trim(); // Remove espaços extras

    if (nome === "") {
        alert("Por favor, insira um nome válido.");
    } else {
        listaDeNomes.push(nome);
        atualizarLista();
        input.value = ""; // Limpa o campo de texto
    }
}

// Função para atualizar a lista visível na página
function atualizarLista() {
    const lista = document.getElementById("lista");
    lista.innerHTML = ""; // Limpa os itens anteriores

    listaDeNomes.forEach(nome => {
        const item = document.createElement("li");
        item.textContent = nome;
        lista.appendChild(item);
    });
}

// Função para sortear um nome
function sortearAmigo() {
    if (listaDeNomes.length === 0) {
        alert("A lista está vazia. Adicione nomes antes de sortear.");
    } else {
        const indiceAleatorio = Math.floor(Math.random() * listaDeNomes.length);
        const nomeSorteado = listaDeNomes[indiceAleatorio];
        document.getElementById("resultado").textContent = `O amigo secreto é: ${nomeSorteado}`;
    }
}
