# 🎨 Estilos em Cascata (CSS3)

## 📌 Introdução
CSS (Cascading Style Sheets) é a tecnologia responsável pela estilização das páginas web. Ele define como os elementos HTML devem ser exibidos na tela, proporcionando controle sobre cores, fontes, espaçamentos e layouts.

---

## 🔹 Modelo de Estilo em Cascata
O termo "cascata" no CSS refere-se à forma como os estilos são aplicados e resolvidos, seguindo uma hierarquia específica:
1. **Ordem de Aparição** – A última regra CSS escrita sobrescreve regras anteriores.
2. **Especificidade** – Quanto mais específico for o seletor, maior prioridade ele terá.
3. **Herança** – Alguns estilos podem ser herdados dos elementos-pai.

---

## 🎯 Regras CSS
Uma regra CSS é composta por **seletor + propriedades + valores**:
```css
seletor {
  propriedade: valor;
}
```
Exemplo:
```css
h1 {
  color: blue;
  font-size: 24px;
}
```
Aqui, todos os `<h1>` da página terão a cor azul e tamanho de fonte 24px.

---

## 🎯 Seletores CSS
Os seletores definem quais elementos HTML serão estilizados. Os principais tipos são:

### 🔹 1. Seletores Simples
- **Por Tag:** Aplica a regra a todas as tags do tipo indicado.
  ```css
  p { color: red; }
  ```
- **Por Classe:** Define estilos para qualquer elemento com a classe especificada.
  ```css
  .destaque { font-weight: bold; }
  ```
- **Por ID:** Aplica o estilo apenas ao elemento com aquele ID.
  ```css
  #titulo { font-size: 32px; }
  ```

### 🔹 2. Seletores Combinadores
- **Descendente:** Seleciona elementos dentro de outros.
  ```css
  div p { color: green; }
  ```
- **Filho Direto:** Seleciona apenas os filhos diretos.
  ```css
  div > p { margin-left: 10px; }
  ```
- **Irmão Adjacente:** Seleciona o primeiro irmão imediato.
  ```css
  h1 + p { font-style: italic; }
  ```

### 🔹 3. Seletores Avançados
- **Pseudo-classes:** Aplicam estilos em estados específicos.
  ```css
  a:hover { color: red; }
  ```
- **Pseudo-elementos:** Estilizam partes específicas de um elemento.
  ```css
  p::first-letter { font-size: 2em; }
  ```

---

## 🎨 Especificidade e Conflitos de Estilo
Quando múltiplas regras competem entre si, o CSS segue uma hierarquia:
1. **Inline (mais forte)** → `style="color: red;"`
2. **ID** (`#meuId`) → Mais forte que classes e tags.
3. **Classe/Pseudo-classe/Atributos** (`.minhaClasse`, `:hover`, `[type="text"]`)
4. **Tag** (`h1`, `p`, `div`)
5. **Herança (menos forte)** → Propriedades herdadas do pai.

> ⚠ **Dica:** Para forçar um estilo, use `!important`, mas evite abusar dessa prática.
```css
p { color: blue !important; }
```

---

## 🛠️ Herança e Propriedades no CSS
### 🔹 Como Funciona a Herança?
A herança no CSS significa que certos estilos aplicados a um elemento-pai podem ser propagados automaticamente para os elementos-filhos. Isso evita a necessidade de repetir regras para múltiplos elementos dentro de um mesmo bloco.

Por padrão, **propriedades relacionadas a texto são herdadas**, enquanto propriedades relacionadas ao layout e ao modelo de caixa **não são herdadas**.

**Exemplo de herança automática:**
```css
body {
  color: darkgray;
  font-family: Arial, sans-serif;
}
p {
  font-size: 18px;
}
```
Neste caso, todos os parágrafos `<p>` herdarão a cor e a fonte do `<body>`, mas o `font-size` só será aplicado explicitamente aos parágrafos.

### 🔹 Propriedades Herdáveis vs. Não Herdáveis
#### **✔️ Propriedades Herdáveis:**
Essas propriedades são geralmente relacionadas a **texto e aparência visual**:
- `color`
- `font`
- `font-family`
- `font-size`
- `visibility`

#### **❌ Propriedades NÃO Herdáveis:**
Essas propriedades são mais focadas em **layout e espaçamento**:
- `margin`
- `padding`
- `border`
- `width`
- `height`
- `display`
- `position`

### 🔹 Controlando a Herança
Se quiser **forçar um elemento a herdar uma propriedade**, use `inherit`:
```css
p {
  color: inherit; /* O parágrafo adotará a cor do elemento pai */
}
```
Se quiser **remover a herança e aplicar o valor padrão do navegador**, use `initial`:
```css
p {
  color: initial; /* Retorna ao valor padrão do navegador */
}
```
Se quiser **garantir que um elemento NÃO herde nada**, use `unset`:
```css
p {
  color: unset; /* Remove qualquer herança e aplica o valor padrão */
}
```

---

## 🚀 Conclusão
CSS é uma ferramenta poderosa para estilizar páginas web, e compreender o modelo de cascata ajuda a resolver conflitos e aplicar estilos corretamente. Dominar seletores e a hierarquia do CSS melhora a organização e eficiência do código.

🔗 **Recursos úteis:**
- [MDN CSS Guide](https://developer.mozilla.org/pt-BR/docs/Web/CSS)
- [CSS Tricks](https://css-tricks.com/)
- [W3Schools CSS](https://www.w3schools.com/css/)

---

✍ **Criado por [Alessandro]** 🚀

