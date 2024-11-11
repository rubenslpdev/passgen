# Gerador de Senhas Seguras

Este é um aplicativo de geração de senhas seguras, desenvolvido com HTML, CSS e JavaScript, que permite a criação de senhas fortes, com diversas opções de personalização. O objetivo é gerar senhas aleatórias e seguras de até 20 caracteres ou mais, garantindo uma camada adicional de proteção para seus dados.

## Funcionalidades

- **Personalização Completa**: Escolha os tipos de caracteres que deseja incluir na senha — letras maiúsculas, letras minúsculas, números e símbolos.
- **Controle de Comprimento**: Ajuste o comprimento da senha conforme necessário através de um controle deslizante, com feedback visual para o usuário.
- **Cópia Rápida**: Copie a senha gerada diretamente para a área de transferência com apenas um clique.
- **Opções Avançadas**: O aplicativo oferece uma seção de configurações avançadas para ajustar detalhes da senha de acordo com as necessidades do usuário.

## Tecnologias Utilizadas

- **HTML** e **CSS**: Interface do usuário e estilos.
- **JavaScript**: Lógica do gerador de senhas, manipulação do DOM e funcionalidades interativas, como a cópia para a área de transferência.

## Exemplo de Código

Aqui está um trecho da função principal responsável pela geração de senhas:

```javascript
function generatePassword(length, lower, upper, number, symbol) {
  let generatedPassword = '';
  const typesCount = lower + upper + number + symbol;
  const typesArr = [{ lower }, { upper }, { number }, { symbol }].filter((item) => Object.values(item)[0]);

  if (typesCount === 0) return '';

  for (let i = 0; i < length; i++) {
    typesArr.forEach((type) => {
      const funcName = Object.keys(type)[0];
      generatedPassword += randomFunc[funcName]();
    });
  }

  return generatedPassword
    .slice(0, length)
    .split('')
    .sort(() => Math.random() - 0.5)
    .join('');
}
```

## Como Usar

1. **Selecione as opções de personalização**: Escolha os tipos de caracteres que a senha deve conter.
2. **Defina o comprimento**: Ajuste o comprimento da senha com o controle deslizante.
3. **Gere e copie**: Clique no botão de "Gerar" para criar uma senha e, em seguida, use o botão de "Copiar" para transferi-la para a área de transferência.
