# Linguagem CSSW

**CSSW** é uma linguagem de preprocessamento CSS que combina CSS tradicional com mixins (`::`) e variáveis (`) para desenvolvimento mais modular e reutilizável.

## 🎯 **Como Funciona**

O preprocessador PHP lê arquivos `.cssw` e os converte para `.css`, processando:
- **Variáveis** com `$variavel`
- **Mixins** com `::mixin`
- **CSS tradicional** mantido intacto

## ⚡ **Sintaxe CSSW**

### 🔧 **CSS Tradicional (Mantido)**
Todo CSS válido funciona normalmente:

```css
.container {
    display: flex;
    justify-content: center;
    background: linear-gradient(45deg, #007bff, #0056b3);
}

@media (max-width: 768px) {
    .container { flex-direction: column; }
}

@keyframes fadeIn {
    from { opacity: 0; }
    to { opacity: 1; }
}
```

### 📦 **Variáveis com `**
Reutilize valores em todo o projeto:

```cssw
/* Uso de variáveis em propriedades CSS */
.div1 {
    background: $principal;
    color: $texto-claro;
    padding: $espacamento-base;
    border-radius: $raio-padrao;
}

.header {
    background: $cor-primaria;
    font-family: $fonte-principal;
    font-size: $tamanho-titulo;
}
```

### 🎨 **Mixins com `::`**
Inclua blocos de CSS reutilizáveis:

```cssw
html, body {
    ::corpo
}

.div1 {
    ::card
    background: $principal;
    height: 500px;
    width: 500px;
}

.botao {
    ::botao-base
    ::sombra-suave
    background: $azul;
    color: $branco;
}
```

## 🔄 **Exemplo Prático: Preprocessamento**

### **Arquivo `.cssw` (entrada):**
```cssw
html, body {
    ::corpo
}

.card-produto {
    ::card
    ::animacao-hover
    background: $branco;
    border: 1px solid $cinza-claro;
    padding: $espacamento-card;
}

.botao-principal {
    ::botao-base
    background-color: $azul;
    color: $branco;
    border-radius: $raio-padrao;
}
```

### **Arquivo `.css` (saída do preprocessador):**
```css
html, body {
    margin: 0;
    padding: 0;
    font-family: Arial, sans-serif;
    line-height: 1.6;
}

.card-produto {
    background: white;
    border-radius: 8px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.1);
    transition: transform 0.3s ease;
    background: #ffffff;
    border: 1px solid #e0e0e0;
    padding: 20px;
}

.card-produto:hover {
    transform: translateY(-2px);
}

.botao-principal {
    display: inline-block;
    padding: 12px 24px;
    border: none;
    cursor: pointer;
    text-decoration: none;
    transition: all 0.3s ease;
    background-color: #007bff;
    color: #ffffff;
    border-radius: 4px;
}
```

## 🚀 **Vantagens do CSSW**

### ✅ **Modularidade**
- **Mixins reutilizáveis**: `::card`, `::botao-base`, `::container-fluid`
- **Variáveis centralizadas**: `$cor-primaria`, `$espacamento-base`
- **Manutenção facilitada**: Altere um mixin e afete todos os usos

### ✅ **Compatibilidade Total**
- **CSS existente**: Funciona sem modificações
- **Frameworks CSS**: Bootstrap, Tailwind, etc. funcionam normalmente
- **Migração gradual**: Adicione CSSW progressivamente

### ✅ **Organização**
- **Separação clara**: Mixins para estrutura, variáveis para valores
- **Reutilização**: Evita repetição de código
- **Consistência**: Padrões visuais unificados

## 🎯 **Casos de Uso**

### 📱 **Sistemas de Design**
```cssw
.componente-card {
    ::card-base
    ::sombra-suave
    ::border-radius-padrao
    background: $card-bg;
    padding: $card-padding;
}

.botao-primario {
    ::botao-base
    ::hover-elevacao
    background: $primario;
    color: $texto-primario;
}
```

### 🎨 **Temas Dinâmicos**
```cssw
.tema-escuro {
    background: $dark-bg;
    color: $dark-text;
}

.tema-claro {
    background: $light-bg;
    color: $light-text;
}
```

### 📐 **Layouts Responsivos**
```cssw
.container {
    ::container-base
    max-width: $max-width-desktop;
}

@media (max-width: 768px) {
    .container {
        ::container-mobile
        padding: $mobile-padding;
    }
}
```

## 💡 **Filosofia**

### **Mixins (`::`) são para:**
- Blocos de CSS reutilizáveis
- Componentes de UI consistentes
- Padrões de layout comuns
- Animações e transições padrão

### **Variáveis (`) são para:**
- Cores do tema
- Espaçamentos e dimensões
- Tipografia (fontes, tamanhos)
- Valores de configuração

### **CSS Tradicional é para:**
- Estrutura base e layout
- Media queries
- Keyframes e animações específicas
- Integração com frameworks

---

CSSW oferece o poder de preprocessamento mantendo a simplicidade e familiaridade do CSS, ideal para projetos que precisam de modularidade sem complexidade excessiva.