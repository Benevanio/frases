# Frases do Dia App

Um aplicativo simples de Flutter que exibe frases motivacionais e permite a geração de novas frases aleatórias ao clicar em um botão.

## Estrutura do Projeto

- **main.dart**: O ponto de entrada do aplicativo, contendo a função `main()` que inicia a execução do Flutter.

- **my_app.dart**: Define a classe principal `MyApp`, que é um widget de estado (`StatefulWidget`). Esta classe gerencia o estado do aplicativo e controla a exibição das frases.

## Funcionalidades

### Frases Aleatórias

O aplicativo exibe uma frase inicial predefinida e uma lista de frases adicionais que podem ser exibidas aleatoriamente. A cada clique no botão "Nova Frase", uma nova frase aleatória é exibida na tela.

```dart
void _gerarNovaFrase() {
  final random = Random();
  setState(() {
    _texto = _frases[random.nextInt(_frases.length)];
  });
}
```

### Interface Gráfica

O design da interface gráfica inclui uma barra de aplicativo (`AppBar`) com um título estilizado, uma área central contendo a frase atual e um botão "Nova Frase". A aparência visual é personalizada com cores e estilos.

```dart
MaterialApp(
  title: "Frases do Dia",
  debugShowCheckedModeBanner: false,
  home: Scaffold(
    appBar: AppBar(
      title: const Center(
        child: Text(
          "Frases do Dia",
          style: TextStyle(
            fontSize: 25,
            fontStyle: FontStyle.italic,
            color: Colors.white,
            decoration: TextDecoration.none,
          ),
        ),
      ),
      backgroundColor: Colors.green,
    ),
    body: // ...
  ),
);
```

### Imagem

O aplicativo inclui a exibição de uma imagem (logo) na parte superior para tornar a interface mais visualmente atraente. Certifique-se de substituir `'images/logo.png'` pelo caminho correto da sua imagem.

```dart
Image(
  image: AssetImage('images/logo.png'),
)
```

### Estilo do Botão

O botão "Nova Frase" tem um estilo personalizado com cores, sombras e tamanho para melhorar a usabilidade.

```dart
ElevatedButton(
  style: ElevatedButton.styleFrom(
    primary: Colors.green,
    onPrimary: Colors.white,
    shadowColor: Colors.black,
    elevation: 15,
  ),
  onPressed: _gerarNovaFrase,
  child: const Text(
    'Nova Frase',
    style: TextStyle(
      fontSize: 25,
      fontStyle: FontStyle.italic,
      color: Colors.white,
      decoration: TextDecoration.none,
    ),
  ),
),
```

## Como Executar

Certifique-se de ter o Flutter instalado em seu ambiente de desenvolvimento. Clone o repositório, navegue até o diretório do projeto e execute:

```bash
flutter run
```

Isso iniciará o aplicativo no emulador ou dispositivo conectado.

Divirta-se explorando frases inspiradoras com o seu aplicativo "Frases do Dia"!