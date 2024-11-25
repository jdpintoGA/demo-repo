# Consultadoria Técnica 25 Novembro - Desenvolvimento Web

Este documento descreve as soluções propostas para as questões abordadas na consultoria de desenvolvimento web. Ele está organizado em tópicos detalhados, abordando problemas técnicos, organização de código, responsividade, acessibilidade e melhores práticas.

---

## 1. Resolução de Problemas Técnicos

### **Quais podem ser os problemas com o Git?**
- **Problemas comuns:**
  - Conflitos de merge
  - Histórico confuso
  - Branches desorganizadas
- **Soluções práticas:**
  1. **Adotar uma estratégia de branching:**
     - Use **Git Flow** ou **Feature Branching**.
     - Exemplo de estrutura: `main`, `develop`, `feature/nome-da-funcionalidade`.
  2. **Evitar conflitos de merge:**
     - Sempre **pull** antes de começar a trabalhar.
     - Divida tarefas para minimizar edições no mesmo arquivo.
  3. **Boas práticas de commits:**
     - Use mensagens claras e descritivas: `git commit -m "Adiciona funcionalidade X ao módulo Y"`.
     - Faça commits pequenos e frequentes.
  4. **Ferramentas complementares:**
     - Use **GitKraken**, **Sourcetree** ou integração do Git no VS Code.

---

## 2. Estruturação e Organização do Código

### **Como organizar o código para torná-lo mais responsivo?**
1. **Unidades relativas:** Substitua `px` por `em`, `rem` ou `%` para facilitar a escalabilidade.
2. **Grid system básico:**
   ```css
   .container {
       display: flex;
       flex-wrap: wrap;
       justify-content: space-between;
   }

## 3. Media Queries: Adapte o layout a diferentes tamanhos de tela:

  ```css
  @media (max-width: 768px) {
      .container {
          flex-direction: column;
      }
  }
  ```

### **Qual o preparo para modularização correta?**
1. Dividir responsabilidades: Separando estilos, scripts e componentes em arquivos próprios.
2. Organizar pastas:
  - `assets/css` para estilos
  - `assets/js` para scripts
  - `components` para HTML reutilizável.
3. Criar um guia para a equipa documentando no `README.md` como cada módulo funciona. 

### **Como melhorar a organização de código no CSS e JavaScript?**
1. No CSS:
 - usar metodologias como BEM (Block, Element, Modifier) para organizar classes.

```css
  .button {
    color: white;
}
.button--primary {
    background-color: blue;
}
```
- Implementar variáveis no CSS.
```css
  :root {
    --primary-color: blue;
}
```

2. No JavaScript:
- Usar funções reutilizáveis. ex
```javascript
function toggleClass(element, className) {
    element.classList.toggle(className);
}
```
- Organizar o código em módulos.

---

## 3. Melhoria de Responsividade e Acessibilidade

### **Como deixar os logos mais responsivos e proporcionais?**
1. Usar unidades relativas para ajustar largura e altura de forma automática.
```css
img {
    max-width: 100%;
    height: auto;
}

```

2. Estabelecer limites no container do logo, como um tamanho máximo proporcional.
```css
.logo-container {
    max-width: 200px;
}

```

### **Quais as melhores práticas de responsividade com foco em acessibilidade?**
1. Garantir contraste de cores suficiente entre texto e fundo. (Contrast Checker ou outra)
2. Testar navegação no site com o teclado para garantir acessibilidade.
3. Fornecer contexto para leitores de tela usando atributos como `aria-labels`.

```html
<button aria-label="Salvar documento">Salvar</button>
```

---

## 4. Práticas de Design e Usabilidade

### **Quais as melhores práticas de uso comercial no design?**
1. Priorizar a hierarquia visual, destacando títulos e CTAs.
2. Realizar testes de usabilidade com usuários reais.
3. Reduzir elementos não essenciais para evitar distrações.

### **Qual a melhor forma de melhorar a velocidade de carregamento de páginas?**
1. Compactar recursos, como imagens e arquivos CSS e JavaScript (TinyPNGs e minifiers).
2. Ativar cache do navegador para armazenar recursos frequentemente usados.
ex apache
3. Implementar o carregamento lento (lazy loading) de imagens para economizar recursos.

```html
<img src="imagem.jpg" loading="lazy" alt="Descrição">
```

---

## 5. Organização de Tarefas e Trabalho em Equipa

### **Como dividir tarefas de desenvolvimento em equipa?**
1. Utilizar ferramentas de gestão como Trello, Notion, Jira para organizar tarefas.
2. Dividir as tarefas de acordo com as habilidades de cada membro da equipa.
3. Definir objectivos para entrega claros e criar checklists para acompanhar o progresso.

---

## 6. Uso de Tecnologias Específicas

### **Quando usar custom elements ou scripts?**
- **Custom elements:**
  - Ideais para criar componentes reutilizáveis, ex: botões personalizados, e quando o scope é limitado a funcionalidades específicas.
- **Scripts:** 
  - São usados para manipular o DOM dinamicamente ou adicionar comportamentos que dependem de interação.

### **Adicionar CSS dinamicamente:**
1. Combine arquivos sempre que possível para reduzir o número de requisições.

  - Exemplo de implementação:

```javascript
function loadCSS(file) {
    const link = document.createElement('link');
    link.rel = 'stylesheet';
    link.href = file;
    document.head.appendChild(link);
}
loadCSS('styles.css');
```

2. Adicione dinamicamente estilos ao carregar páginas ou componentes específicos.


