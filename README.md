# Calculadora Simples
## Link do projeto: https://jonas1berto.github.io/calculadora/
#
### Selecionando o input, e iniciando a calculadora
```
    this.display = document.querySelector('.display');

    this.inicia = () => {
      this.display.focus();
      this.cliqueBotoes();
      this.pressionaEnter();
    };
```

### Realizando o evento de click, e imprimindo o valor na tela.
```
   this.cliqueBotoes = () => {
      document.addEventListener('click', e => {
        const el = e.target

        if(el) {
          this.display.focus();
        }

        if (el.classList.contains('btn-number')) {
          btnParaDisplay(el.innerText)
        }

        if (el.classList.contains('btn-clear')) {
          this.clearDisplay()
        }

        if (el.classList.contains('btn-del')) {
          this.clearOne()
        }

        if(el.classList.contains('btn-eq')) {
          this.realizaConta();
        }
      });
    };

    btnParaDisplay = (valor) => {
      this.display.value += valor
      this.display.focus()
    }
  }
```

### Realizando a conta com o valor obtido do input, e retornando o error quando a conta n for válida.
```
this.realizaConta = () => {
      let conta = this.display.value;

      try {
        conta = eval(conta);

        if(!conta) {
          alert('Conta inválida');
          return;
        }

        this.display.value = conta
      } catch(e) {
        this.display.value = ''
        alert('Conta inválida');
        return
      }
    };
```

## Projeto realizado para solidificar meus conhecimentos em Logica de programação, HTML, CSS e JavaScript.
## Tecnologias usadas no Projeto
- ![HTML5](https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white)   
- ![CSS3](https://img.shields.io/badge/css3-%231572B6.svg?style=for-the-badge&logo=css3&logoColor=white)    
- ![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E)
