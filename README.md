# DSList - Intensivão Java Spring

[![NPM](https://img.shields.io/npm/l/react)](https://github.com/devbruto93/dslist/blob/main/LICENSE) 

Olá! Este repositório contém o projeto **DSList**, desenvolvido durante o **Intensivão Java Spring**, ministrado pelo professor [Nélio Alves](https://github.com/acenelio). 

Foram 5 dias de muito aprendizado, com foco total no **backend em Java**, utilizando o framework **Spring Boot**. Além do conteúdo técnico, também foram abordadas boas práticas de programação, construção de portfólio, dicas para o LinkedIn e orientações sobre o mercado de trabalho.

Sou aluno do Nélio em outro curso de Java na Udemy e posso afirmar que sua didática e clareza são excepcionais. Essa imersão foi extremamente valiosa para minha evolução como desenvolvedor.

---

## 🚀 Sobre o Projeto

O **DSList** é uma aplicação de lista de jogos, onde é possível visualizar:

- Título
- Gênero
- Plataforma
- Data de lançamento
- Breve descrição

A aplicação conta com **algoritmos de busca** para facilitar a navegação pelos jogos e um destaque especial a funcionalidade de **reordenar jogos na lista** com base na posição desejada, simulando um sistema de "arrastar e soltar".

---

## 🧠 Algoritmo de "Arrastar e Soltar"

Esse foi o ponto do projeto que mais me chamou atenção. Até então, eu estava estudando conteúdos mais básicos, e essa funcionalidade me tirou da zona de conforto.

O algoritmo permite **mover um item de uma posição para outra dentro da mesma lista**. Pode parecer simples, mas durante a explicação, o professor destacou que não é algo trivial e realmente exigiu bastante atenção da minha parte para compreender completamente.

### 🧩 Código:

```java
public void move(Long listId, int sourceIndex, int destinationIndex) {
    List<GameMinProjection> list = gameRepository.searchByList(listId);

    GameMinProjection obj = list.remove(sourceIndex);
    list.add(destinationIndex, obj);

    int min = Math.min(sourceIndex, destinationIndex);
    int max = Math.max(sourceIndex, destinationIndex);

    for (int i = min; i <= max; i++) {
        gameListRepository.updateBelongingPosition(listId, list.get(i).getId(), i);
    }
```

Esse trecho de código representa mais do que uma funcionalidade para mim, simboliza progresso. Ter compreendido e implementado esse algoritmo foi uma pequena vitória pessoal que quis compartilhar com vocês.

🛠 Tecnologias Utilizadas

Java

Spring Boot

JPA / Hibernate

Maven

🙏 Agradecimentos

Meus sinceros agradecimentos ao professor e doutor Nélio Alves pela iniciativa, dedicação e qualidade no ensino. Mesmo em apenas 5 aulas, a experiência foi transformadora.

👤 Autor
Douglas Modesto Eugênio
www.linkedin.com/in/douglasmodesto93
