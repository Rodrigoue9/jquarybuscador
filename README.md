<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>

    <title>Document</title>
</head>
<body>
    
    <input type="text" id="searchInput" placeholder="Digite sua pesquisa">
    <ul id="searchResults"></ul>
    
    <ul>
      <li class="searchable-element">Item 1</li>
      <li class="searchable-element">Item 2</li>
      <li class="searchable-element">Item 3</li>
      <li class="searchable-element">Item 4</li>
      <li class="searchable-element">Item 5</li>
    </ul>
    
    <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
    <script>
    $(document).ready(function() {
      $('#searchInput').on('keyup', function() {
        var searchText = $(this).val().toLowerCase();
        $('#searchResults').empty();
        
        // Filtra os elementos desejados e exibe os resultados correspondentes
        $('li.searchable-element').each(function() {
          var text = $(this).text().toLowerCase();
          if (text.indexOf(searchText) !== -1) {
            $('#searchResults').append('<li>' + text + '</li>');
          }
        });
      });
    });
    </script>
</body>
</html>
