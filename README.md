# David-Lucas
Loja do Palmeiras
<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Loja Palmeiras</title>
<style>
body {
font-family: Arial, sans-serif;
margin: 0;
padding: 0;
}

header {
background-color: #4CAF50;
color: white;
padding: 15px;
text-align: center;
}

nav a {
color: white;
margin: 0 15px;
text-decoration: none;
}

.produto {
border: 1px solid #ccc;
margin: 10px;
padding: 10px;
display: inline-block;
text-align: center;
}

footer {
text-align: center;
padding: 10px;
background-color: #f1f1f1;
position: relative;
bottom: 0;
width: 100%;
}
</style>
</head>
<body>

<!-- Página Inicial -->
<header>
<h1> Seja Bem-vindo à Melhor Loja de Produtos Oficiais do Palmeiras</h1>
<nav>
<a href="#produtos">Produtos</a>
<a href="#carrinho">Carrinho</a>
</nav>
</header>
<main>
<h2>Explore nossos produtos!</h2>
<p>Oferecemos uma grande variedade de produtos do palmeiras de alta qualidade.</p>
</main>

<!-- Página de Produtos -->
<section id="produtos">
<h1>Produtos Disponíveis</h1>
<div class="produto">
<img src="https://images.puma.com/image/upload/f_auto,q_auto,b_rgb:fafafa/global/777237/01/fnd/BRA/w/1000/h/1000/fmt/png" alt="Produto 1">
<h3>Produto 1</h3>
<p>Preço: R$ 10,00</p>
<input type="number" id="quantidade1" min="1" value="1">
<button onclick="adicionarAoCarrinho('Produto 1', 10, quantidade1.value)">Adicionar ao Carrinho</button>
</div>
<div class="produto">
<img src="https://upsports.vtexassets.com/arquivos/ids/197900/CAMISA-PALMEIRAS-TORCEDOR-AWAY-JERSEY-24-777262-01-WHITE-XGG.jpg?v=638602784408970000">
<h3>Produto 2</h3>
<p>Preço: R$ 15,00</p>
<input type="number" id="quantidade2" min="1" value="1">
<button onclick="adicionarAoCarrinho('Produto 2', 15, quantidade2.value)">Adicionar ao Carrinho</button>
</div>
</section>

<!-- Página do Carrinho -->
<section id="carrinho">
<h1>Carrinho de Compras</h1>
<h2>Itens no Carrinho:</h2>
<div id="carrinhoDiv"></div>
<button onclick="finalizarCompra()">Finalizar Compra</button>
</section>

<footer>
<p>&copy; 2024 Palmeiras</p>
</footer>

<script>
let carrinho = [];

function adicionarAoCarrinho(nome, preco, quantidade) {
const item = { nome, preco, quantidade: parseInt(quantidade) };
carrinho.push(item);
alert(`${quantidade} ${nome}(s) adicionado(s) ao carrinho!`);
mostrarCarrinho();
}

function mostrarCarrinho() {
const carrinhoDiv = document.getElementById('carrinhoDiv');
carrinhoDiv.innerHTML = '';
let total = 0;

carrinho.forEach(item => {
const totalItem = item.preco * item.quantidade;
total += totalItem;
carrinhoDiv.innerHTML += `<p>${item.quantidade} x ${item.nome} - R$ ${totalItem.toFixed(2)}</p>`;
});

carrinhoDiv.innerHTML += `<h3>Total: R$ ${total.toFixed(2)}</h3>`;
}

function finalizarCompra() {
alert('Compra finalizada com sucesso!');
carrinho = [];
mostrarCarrinho();
}

document.addEventListener('DOMContentLoaded', mostrarCarrinho);
</script>

</body>
</html>
