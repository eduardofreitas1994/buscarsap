# buscarsap
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Busca de Código</title>
    <style>
        /* Estilo para a barra de busca */
        #search-bar {
            margin: 20px;
            padding: 10px;
        }

        /* Estilo para os itens da lista de resultados */
        .code-item {
            display: none; /* Inicialmente ocultos */
            margin-bottom: 10px;
        }
    </style>
</head>
<body>
    <h1>Buscar de Código SAP</h1>

    <!-- Barra de busca -->
    <input type="text" id="search-bar" placeholder="Digite o código">
    
    <!-- Lista de códigos -->
    <ul id="code-list">
        <li class="code-item">FITA ISOLANTE: ABC123</li>
        <li class="code-item">PARAFUSO: XYZ789</li>
        <li class="code-item">CONTATOR: 123DEF</li>
        <li class="code-item">DISJUNTOR: QWE456</li>
    </ul>

    <script>
        // Função para realizar a busca
        function searchCode() {
            // Obtém o valor digitado pelo usuário na barra de busca
            var searchText = document.getElementById("search-bar").value.toUpperCase();

            // Obtém a lista de itens
            var items = document.getElementsByClassName("code-item");

            // Itera sobre os itens da lista e mostra/oculta com base na busca
            for (var i = 0; i < items.length; i++) {
                var item = items[i];
                var text = item.textContent || item.innerText;
                if (text.toUpperCase().indexOf(searchText) > -1) {
                    item.style.display = "block";
                } else {
                    item.style.display = "none";
                }
            }
        }

        // Adiciona um ouvinte de evento para chamar a função de busca quando o usuário digitar na barra
        document.getElementById("search-bar").addEventListener("input", searchCode);
    </script>
</body>
</html>
