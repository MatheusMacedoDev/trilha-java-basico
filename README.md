# Diagrama de classes Iphone
```
classDiagram
    class ReprodutorMusical {
        -artistas: List~Artista~
        -musicas: List~Musica~

        +tocar()
        +pausar()
        +selecionarMusica(Musica musica)
        +listarArtistas() List~Artista~
        +listarMusicas() List~Musica~
    }

    class Artista {
        -nome: String
        -musicas: List~Musica~
    }

    class Musica {
        -nome: String
        -autor: Artista
    }

    class AparelhoTelefonico {
        -contatos: List~Contato~
        -contatosFavoritos: List~Contato~

        +ligar(String numero)
        +atender()
        +iniciarCorreioVoz()
        +listarContatos() List~Contato~
    }

    class Contato {
        -nome: String
        -telefone: String

        +getNome()
        +getTelefone()
    }

    class NavegadorInternet {
        +adicionarNovaAba()
        +atualizarPagina()
        +exibirPagina(String url)
        +aplicarZoomPaginaAtual()
    }

    class iPhone {
        +ReprodutorMusical: ReprodutorMusical
        +AparelhoTelefonico: AparelhoTelefonico
        +NavegadorInternet: NavegadorInternet

        +desbloquearTela()
        +desligarTela()
    }

    iPhone --*  ReprodutorMusical
    iPhone --* AparelhoTelefonico
    iPhone --* NavegadorInternet

    ReprodutorMusical o-- Artista
    ReprodutorMusical o-- Musica

    Artista o-- Musica
    Musica o-- Artista

    AparelhoTelefonico o-- Contato
```
