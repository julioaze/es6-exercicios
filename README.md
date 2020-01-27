# Exercícios resolvidos #

**Exercício 1**
```js
class Usuario {
  constructor(email, senha) {
    this.email = email;
    this.senha = senha;
  }

  isAdmin() {
    return this.admin === true;
  }
}

class Admin extends Usuario {
  constructor(email, senha) {
    super(email, senha);

    this.admin = true;
  }
}

const User1 = new Usuario("email@teste.com", "senha123");
const Adm1 = new Admin("email@teste.com", "senha123");

console.log(User1.isAdmin()); // false
console.log(Adm1.isAdmin()); // true
```

**Exercício 2**
```js
const usuarios = [
  { nome: "Diego", idade: 23, empresa: "Rocketseat" },
  { nome: "Gabriel", idade: 15, empresa: "Rocketseat" },
  { nome: "Lucas", idade: 30, empresa: "Facebook" }
];

// 2.1

const idades = usuarios.map(usuario => usuario.idade);
console.log(idades);

// 2.2

const rocketseat18 = usuarios.filter(
  usuario => usuario.empresa === "Rocketseat" && usuario.idade >= 18
);
console.log(rocketseat18);

// 2.3

const google = usuarios.find(usuario => usuario.empresa === "Google");
console.log(google);

// 2.4

const calculo = usuarios
  .map(usuario => ({ ...usuario, idade: usuario.idade * 2 }))
  .filter(usuario => usuario.idade <= 50);

console.log(calculo);
```

**Exercício 3**
```js
// 3.1

const arr = [1, 2, 3, 4, 5];

arr.map(item => item + 10);

// 3.2

const usuario = { nome: "Julio", idade: 25 };

const mostraIdade = usuario => usuario.idade;

mostraIdade(usuario);

// 3.3

const nome = "Diego";
const idade = 23;

const mostraUsuario = (nome = "Julio", idade = 25) => ({
  nome,
  idade
});

mostraUsuario(nome, idade);
mostraUsuario(nome);

// 3.4

const promise = () => new Promise((resolve, reject) => resolve());
```

**Exercício 4**
```js
// 4.1

const empresa = {
  nome: "Rocketseat",
  endereco: {
    cidade: "Rio do Sul",
    estado: "SC"
  }
};

const {
  nome,
  endereco: { cidade, estado }
} = empresa;

console.log(nome); // Rocketseat
console.log(cidade); // Rio do Sul
console.log(estado); // SC

// 4.2

function mostraInfo({ nome, idade }) {
  return `${nome} tem ${idade} anos.`;
}

mostraInfo({ nome: "Diego", idade: 23 });
```

**Exercício 5**
```js
// 5.1 A

const arr = [1, 2, 3, 4, 5, 6];

const [x, ...y] = arr;

console.log(x); // 1
console.log(y); // [2, 3, 4, 5, 6]

// 5.1 B

function soma(...nums) {
  return nums.reduce((a, b) => a + b);
}

console.log(soma(1, 2, 3, 4, 5, 6)); // 21
console.log(soma(1, 2)); // 3

// 5.2

const usuario = {
  nome: "Diego",
  idade: 23,
  endereco: {
    cidade: "Rio do Sul",
    uf: "SC",
    pais: "Brasil"
  }
};

const usuario2 = { ...usuario, nome: "Gabriel" };
const usuario3 = {
  ...usuario,
  endereco: { ...usuario.endereco, cidade: "Lontras" }
};
```

**Exercício 6**
```js
const usuario = "Diego";
const idade = 23;

console.log(`O usuário ${usuario} possui ${idade} anos`);
```

**Exercício 7**
```js
const nome = "Diego";
const idade = 23;

const usuario = {
  nome,
  idade,
  cidade: "Rio do Sul"
};
```
