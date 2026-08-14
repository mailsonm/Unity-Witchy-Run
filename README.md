# Unity-Witchy-Run 🧹🧙‍♀️

**Unity-Witchy-Run** é a versão em **Unity 2D (C#)** do jogo da bruxinha (*Endless Runner 2D*), desenvolvida originalmente em **Julho de 2023** por **Mailson Maia Alves** para explorar a engine Unity, renderização 2D URP, física de Rigidbodies e conciliação de animações/parallax.

> 💬 **Nota do Desenvolvedor:**  
> *"Ao revisitar este projeto em 2026, realizei apenas pequenas correções de manutenção e padronização de scripts C#. Vale ressaltar que este repositório foi construído originalmente em 2023 apenas para fins de aprendizado e exploração pessoal da engine Unity, e não com o intuito de ser um jogo comercial completo de mercado."*

---

## 📜 Histórico de Aprendizado & Recursos Explorados (2023 - 2024)

Este projeto foi construído na **Unity 2022.3.3f1** utilizando o pipeline 2D (URP):

1. **Efeito Parallax 2D (`Parallax01.cs`):**  
   Composição de camadas de cenário em profundidade 3D/2D utilizando a textura com `Warp Mode: Repeat` para garantir rolagem contínua sem rastro (*seam*).
2. **Controle de Física e Animação do Personagem (`PersonagemMovimento.cs`):**  
   Movimentação via `Rigidbody2D`, espelhamento do `SpriteRenderer.flipX` e detecção de solo nos pés do personagem via `Physics2D.OverlapCircle`.
3. **Spawning de Inimigos Ponderado (`GeradorDeInimigos.cs`):**  
   Sistema de geração de ondas com seleção aleatória ponderada baseada em pesos (`PesoInimigo.cs`).
4. **Interface e Sistema de Pontuação (`Pontuacao.cs` & `GerenciadorPartida.cs`):**  
   Integração com **TextMeshPro** para contagem de pontuação progressiva e gerenciamento de transição de telas.

---

## 🛠️ Revisão de Manutenção (Agosto de 2026)

Em **14 de Agosto de 2026**, o repositório passou por uma revisão técnica de organização e prevenção de bugs:

1. **Padronização de Nomenclatura C#:** Remoção de scripts legados duplicados com erros de digitação (`PersonagemMovitento01.cs`) e padronização das referências da classe `PersonagemMovimento`.
2. **Correção de Coordenadas de Spawn:** Ajuste nos limites de parâmetros no `Random.Range` do `GeradorDeInimigos.cs` para evitar erros de limites.
3. **Reinicialização Segura do Time Scale:** Garantida a reinicialização de `Time.timeScale = 1f` ao recarregar a partida no `GerenciadorPartida.cs`, prevenindo que a cena fique congelada após um Game Over.

---

## 📁 Estrutura do Projeto Unity

```text
Unity-Witchy-Run/
├── DiarioDeBordo.txt                # Anotações originais do desenvolvimento em 2023
├── README.md                        # Guia principal do repositório
├── CLAUDE.md                        # Documentação técnica e arquitetura do projeto
└── Witchy-Run/                      # Projeto Unity
    ├── Assets/
    │   ├── Cenario/                 # Texturas do Parallax Forest Background
    │   ├── Prefabs/                 # Prefabs do Personagem e Inimigos
    │   ├── Scenes/                  # Cenas da Unity (Menu, Gameplay)
    │   ├── Scripts/                 # Scripts C# da lógica do jogo
    │   ├── Music/                   # Trilhas sonoras e efeitos de áudio
    │   └── TextMesh Pro/            # Recursos visuais de tipografia
    └── ProjectSettings/             # Configurações globais da Unity
```

---

## 👤 Autor

* **Desenvolvedor:** Mailson Maia Alves  
* **GitHub:** [@mailsonm](https://github.com/mailsonm)
