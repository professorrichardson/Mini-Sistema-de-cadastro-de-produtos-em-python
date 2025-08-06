

# 🛍️ Mini Sistema de Cadastro de Produtos em Python

Seja bem-vindo(a) ao seu **primeiro projetinho prático em Python**! Aqui, você vai aprender como **armazenar produtos**, **ler arquivos**, **usar tuplas** e **manipular strings**, tudo com um código simples e fácil de entender.

---

## 🚀 O que você vai aprender

✅ Manipular **strings**  
✅ Criar e acessar **tuplas**  
✅ Trabalhar com **arquivos** de texto (.txt)  
✅ Escrever **funções**  
✅ Estruturar um programa em **paradigma procedural** (passo a passo)

---

## 🧠 Como funciona o sistema?

Vamos entender o que o código faz em partes, como um tutorial.

---

### 1. ✨ Função para formatar nomes

```python
def formatar_nome(nome):
    return nome.strip().title()
```

📝 **O que faz?**  
Remove espaços antes/depois e coloca a primeira letra em maiúscula.  
Exemplo: `" banana "` → `"Banana"`

---

### 2. 📥 Função para cadastrar produtos

```python
def cadastrar_produto():
    nome = input("Digite o nome do produto: ")
    preco = float(input("Digite o preço do produto: "))
    categoria = input("Digite a categoria do produto: ")
    return (formatar_nome(nome), preco, categoria)
```

📝 **O que faz?**  
Pede 3 informações ao usuário e retorna em uma **tupla**:
```python
("Banana", 3.5, "Fruta")
```

---

### 3. 💾 Função para salvar os dados em um arquivo `.txt`

```python
def salvar_produto(produto):
    with open("produtos.txt", "a", encoding="utf-8") as arquivo:
        linha = f"{produto[0]};{produto[1]};{produto[2]}\n"
        arquivo.write(linha)
```

📝 **O que faz?**  
Abre (ou cria) o arquivo `produtos.txt` e **adiciona o produto** como texto separado por `;`.

---

### 4. 📃 Função para listar os produtos

```python
def listar_produtos():
    try:
        with open("produtos.txt", "r", encoding="utf-8") as arquivo:
            for linha in arquivo:
                nome, preco, categoria = linha.strip().split(";")
                print(f"Produto: {nome} | Preço: R${preco} | Categoria: {categoria}")
    except FileNotFoundError:
        print("Nenhum produto cadastrado ainda.")
```

📝 **O que faz?**  
Lê o arquivo e **mostra os produtos** na tela formatados.  
Se não existir o arquivo, mostra uma mensagem amigável.

---

### 5. 🧭 Menu principal (interface de texto)

```python
while True:
    print("\n1 - Cadastrar produto")
    print("2 - Listar produtos")
    print("0 - Sair")
    opcao = input("Escolha: ")

    if opcao == "1":
        produto = cadastrar_produto()
        salvar_produto(produto)
    elif opcao == "2":
        listar_produtos()
    elif opcao == "0":
        break
```

📝 **O que faz?**  
Um menu que **roda para sempre** (até digitar 0).  
O usuário escolhe se quer:
- Cadastrar produtos
- Ver produtos salvos
- Sair

---

## 🗂️ Estrutura dos arquivos gerados

- `produtos.txt`: guarda os produtos cadastrados no formato:
```
Banana;3.5;Fruta
Arroz;8.99;Alimento
```

---

## 🧪 Dica para testar

1. Rode o programa (`python nome_do_arquivo.py`)
2. Escolha `1` e cadastre alguns produtos
3. Escolha `2` para ver todos que já foram salvos
4. Olhe o arquivo `produtos.txt` criado automaticamente!

---

## 🎓 Próximos passos

Se você entender esse código, você pode:
- Criar filtros por categoria
- Fazer edição de produtos
- Refatorar usando orientação a objetos (veja a Parte 2 no repositório!)

---

## 🤘 Bora codar!

Não se preocupe em errar. O mais importante é **praticar e entender** o que está fazendo.  
Qualquer dúvida, volte nos comentários do código ou pergunte! 🚀

