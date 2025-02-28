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

## 🎯 Especificidade e Conflitos de Estilo
Quando múltiplas regras competem entre si, o CSS segue uma hierarquia baseada na **especificidade**. O modelo de especificidade é representado como uma **tríade de valores (a, b, c)**, onde:

- **a (ID selectors)** → Contagem de seletores `id`
- **b (Class, Attribute, Pseudo-class selectors)** → Contagem de classes, atributos e pseudo-classes
- **c (Type selectors and Pseudo-elements)** → Contagem de seletores de tag e pseudo-elementos

### Exemplo prático de especificidade
Vamos considerar o seguinte código:

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <link rel="stylesheet" href="styles.css"> <!-- Arquivo CSS externo -->
    <style>
        /* Especificidade: (0,0,1) */
        h1 { color: blue; }
        
        /* Especificidade: (0,1,0) */
        .titulo { color: green; }
        
        /* Especificidade: (1,0,0) */
        #principal { color: red; }
    </style>
</head>
<body>
    <h1 id="principal" class="titulo" style="color: purple;">Texto de exemplo</h1>
</body>
</html>
```

### Como o CSS decide a cor final do `<h1>`?
1. **`h1 { color: blue; }`** → Especificidade **(0,0,1)**
2. **`.titulo { color: green; }`** → Especificidade **(0,1,0)** (prioridade maior que a anterior)
3. **`#principal { color: red; }`** → Especificidade **(1,0,0)** (prioridade ainda maior)
4. **`style="color: purple;"`** → Especificidade **(1,0,0,0)** (inline sempre vence qualquer regra externa, a menos que haja `!important`)

### Resultado final
O `h1` terá a cor **purple** porque o estilo inline tem a maior prioridade.

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

### Exemplo prático de aplicação de estilos
CSS pode ser aplicado de três formas:
1. **Inline** (`style=""` dentro do HTML)
   ```html
   <h1 style="color: red;">Título em vermelho</h1>
   ```
   - **Especificidade: (1,0,0,0)** (prioridade máxima)

2. **Interno** (`<style>` dentro do `<head>`)
   ```html
   <head>
       <style>
           h1 { color: blue; }
       </style>
   </head>
   ```
   - **Especificidade: (0,0,1)**

3. **Externo** (Arquivo `.css` separado e referenciado no `<head>`) 
   ```html
   <head>
       <link rel="stylesheet" href="styles.css">
   </head>
   ```
   ```css
   h1 { color: green; }
   ```
   - **Especificidade: (0,0,1)** (mesmo peso do interno, mas pode ser sobrescrito pela ordem de carregamento)

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
