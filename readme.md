# Manipulação de array com map, forEach, filter e reduce

```
const empresas = [
    { nome:'Samsung',valorDeMercado: 50, CEO: 'Kim Hyun Suk', anoDeCriacao: 1938},
    { nome: 'Microsoft',valorDeMercado: 415, CEO: 'Satya Nadella', anoDeCriacao: 1975 },
    { nome: 'Intel',valorDeMercado: 117, CEO:'Brian Krzanich', anoDeCriacao: 1968},
    { nome: 'Facebook',valorDeMercado: 383, CEO:'Mark Zuckerberg', anoDeCriacao: 2004},
    { nome: 'Spotify',valorDeMercado: 30, CEO:'Daniel Ek', anoDeCriacao: 2006  },
    {nome: 'Apple', valorDeMercado: 845, CEO: 'Tim Cook', anoDeCriacao: 1976}
];
```

O código deve exibir as seguintes informações:

- Empresas criadas depois dos anos 2000.
- O nome de cada empresa e de seu CEO.
- O valor de todas as empresas somadas.

# Filter

Ele vai percorrer todo o array e criar um novo com todos os elementos que passaram no teste implementado, no nosso caso, quando ano de criação for maior que 2000.

```
empresas.anoDeCriacao
```

Agora basta criar a condição para exibir o anoDeCriacao maior que 2000, dentro do filter:

```
const anoDeCriacao = empresas.filter(empresa => (empresa.anoDeCriacao > 2000));

console.log( anoDeCriacao );
```

Resposta:

```
[ { nome: 'Facebook',
    valorDeMercado: 383,
    CEO: 'Mark Zuckerberg',
    anoDeCriacao: 2004 },
  { nome: 'Spotify',
    valorDeMercado: 30,
    CEO: 'Daniel Ek',
    anoDeCriacao: 2006 } ]
```

# Map

Com map é possível percorrer todos os item do array, executar alguma transformação nesses itens e retornar um novo array sem modificar o atual, vamos percorrer o array e dentro de cada objeto vamos pegar as propriedades nome e CEO de cada empresa.

```
const exibeInformacoes = empresas.map( empresa => `${empresa.nome}` + ' CEO: ' + `${empresa.CEO}`);
console.log( exibeInformacoes )
```

Resposta:

```
[ 'Samsung CEO: Kim Hyun Suk',
  'Microsoft CEO: Satya Nadella',
  'Intel CEO: Brian Krzanich',
  'Facebook CEO: Mark Zuckerberg',
  'Spotify CEO: Daniel Ek',
  'Apple CEO: Tim Cook' ]
```

# Reduce

O reduce passa por cada item do array fazendo uma expressão escolhida, e no final vai devolver um único valor. Ele recebe dois valores, um acumulado e um atual, no nosso caso o acumulado irá somar com o atual. Como no primeiro loop da soma não temos nenhum valor acumulado, então precisamos passar como segundo parâmetro esse valor, que no nosso caso vai ser 0. Se não tivéssemos passado um valor de acumulado o reduce pegaria o primeiro item do array, tomando o como se fosse o valor acumulado.
Nosso código ficou terminado ficou assim:

```
const total = empresas.reduce((resultado, quantidade) => {
    return (resultado + quantidade.valorDeMercado ’);
}, 0);
```

Resposta:

```
console.log( total )
//1840
```

# forEach

O forEach percorre todos os itens de um array, tal como o loop for normal, isso é porque internamente ele possui um lop for.

```
empresasNome.forEach(function (nome, i) {
  console.log(`Nome ${i}:`, nome);
  
  // Resposta:
  //Nome 0: Samsung
  // Nome 1: Microsoft
  // Nome 2: Intel
  // Nome 3: Facebook
  // Nome 4: Spotify
  // Nome 5: Apple
});
```
