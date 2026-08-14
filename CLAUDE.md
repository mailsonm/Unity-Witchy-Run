# Unity-Witchy-Run - CLAUDE.md

## 1. Overview / Resumo
**[PT-BR]** Projeto de jogo 2D desenvolvido na engine **Unity 2022.3.3f1** utilizando linguagem C# e pipeline 2D (Universal Render Pipeline). O projeto implementa mecânicas de corrida infinita (Endless Runner) com rolagem parallax de cenários, controle de física 2D via Rigidbody2D, animações por estados e sistema de spawning ponderado de inimigos.

---

## 2. Technical Stack
- **Engine**: Unity 2022.3.3f1 (2D URP)
- **Language**: C# (.NET Standard / Mono)
- **Physics**: Unity Physics2D (`Rigidbody2D`, `BoxCollider2D`, `CircleCollider2D`)
- **UI**: TextMeshPro (`TMP_Text`)

---

## 3. Key Components & Architecture

### Physics & Input (`PersonagemMovimento.cs`)
- `Rigidbody2D` com força vertical via `AddForce(Vector2.up * 600)` para pulos.
- `Physics2D.OverlapCircle` no transform `peDoPersonagem` contra a camada `chaoLayer` para validação de grounding.

### Enemy Spawner (`GeradorDeInimigos.cs` & `PesoInimigo.cs`)
- Spawning periódico via Corrotina (`WaitForSeconds`).
- Seleção por peso acumulado (`GetInimigo()`) selecionando dinamicamente entre prefabs de inimigos terrestres e aéreos.

### Game State Management (`GerenciadorPartida.cs` & `PersonagemColisao.cs`)
- Controle de ciclo de vida com `Time.timeScale` (congelamento no Game Over e restauração em `1f` na reinicialização).
