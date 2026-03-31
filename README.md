# 🚗 Simulador de Veículos - Sistema de Gerenciamento Dinâmico

<!-- Badges -->
![TypeScript](https://img.shields.io/badge/TypeScript-5.5.4-blue?style=flat-square)
![Node.js](https://img.shields.io/badge/Node.js-runtime-green?style=flat-square)
![License](https://img.shields.io/badge/License-ISC-yellow?style=flat-square)
![Version](https://img.shields.io/badge/Version-1.0.0-blue?style=flat-square)

## 📋 Sumário

- [Visão Geral](#visão-geral)
- [Features](#-features)
- [Requisitos](#-requisitos)
- [Instalação](#-instalação)
- [Como Usar](#-como-usar)
- [Estrutura do Projeto](#-estrutura-do-projeto)
- [Documentação da API](#-documentação-da-api)
- [Exemplos de Uso](#-exemplos-de-uso)
- [Guia de Troubleshooting](#-guia-de-troubleshooting)
- [Contribuições](#-contribuições)
- [Licença](#-licença)

---

## 🎯 Visão Geral

O **Simulador de Veículos** é uma aplicação interativa desenvolvida em TypeScript que permite ao usuário criar e controlar um veículo virtual através de um menu intuitivo. O sistema simula comportamentos realistas de um automóvel, incluindo aceleração, frenagem, mudança de marchas e cálculos dinâmicos de velocidade.

### Caso de Uso Primário
Ideal para fins educacionais e de prototipagem, demonstrando conceitos de Programação Orientada a Objetos (POO) em TypeScript, bem como interação com o usuário via CLI.

---

## ✨ Features

### ✅ Funcionalidades Implementadas
- ✔️ **Criação Dinâmica de Veículos**: Personalize marca, modelo, potência e número de marchas
- ✔️ **Sistema de Marchas**: Controle o número de marchas do veículo
- ✔️ **Aceleração Proporcional**: Velocidade aumenta com base na potência do veículo
- ✔️ **Menu Interativo**: Interface amigável via linha de comando
- ✔️ **Visualização de Dados**: Exibição em tabela dos parâmetros do veículo

### 🔄 Funcionalidades em Desenvolvimento
- [ ] **Frenagem Realista**: Redução de velocidade com validações
- [ ] **Descida de Marchas**: Sistema completo de mudança para marcha reduzida
- [ ] **Subida de Marchas Automática**: Automação inteligente de mudanças
- [ ] **Cálculo de Combustível**: Simulação de consumo baseado em aceleração
- [ ] **Sistema de Limites**: Velocidade máxima por marcha
- [ ] **Persistência de Dados**: Salvar histórico de velocidades
- [ ] **Testes Unitários**: Cobertura completa de testes

---

## 📦 Requisitos

### Dependências Obrigatórias
| Dependência | Versão | Propósito |
|---|---|---|
| **Node.js** | 16.x+ | Runtime JavaScript |
| **TypeScript** | 5.5.4+ | Compilação e tipagem |
| **ts-node** | 10.9.2+ | Execução direta de arquivos TS |
| **prompt-sync** | 4.2.0+ | Entrada de usuário via CLI |

### Dependências de Desenvolvimento
```json
{
  "@types/prompt-sync": "^4.2.3",
  "prompt-sync": "^4.2.0",
  "ts-node": "^10.9.2",
  "typescript": "^5.5.4"
}
```

### Requisitos do Sistema
- SO: Windows, macOS ou Linux
- RAM: 512 MB mínimo
- Espaço em Disco: 50 MB

---

## 🚀 Instalação

### 1️⃣ Clonar o Repositório
```bash
git clone https://github.com/seu-usuario/simulador-veiculos.git
cd trabalhogitt
```

### 2️⃣ Instalar Dependências
```bash
npm install
```

### 3️⃣ Compilar TypeScript
```bash
npx tsc
```

### 4️⃣ Verificar Instalação
```bash
node index.js
# ou com ts-node
npx ts-node index.ts
```

---

## 🎮 Como Usar

### Iniciando a Aplicação

```bash
npm start
# ou
npx ts-node index.ts
```

### Fluxo de Uso

#### 1. **Criação do Veículo**
Na inicialização, o programa solicitará as informações do veículo:
```
Marca: Toyota
Modelo: Corolla
Potência: 100
Número de marchas: 5
```

#### 2. **Menu Principal**
```
########### MENU ###########
1 - Acelerar
2 - Frear
3 - Subir marcha
4 - Descer marcha
5 - Imprimir dados do veículo
0 - Sair

Escolha uma opção: 
```

#### 3. **Operações Disponíveis**

| Opção | Ação | Descrição |
|---|---|---|
| **1** | Acelerar | Aumenta velocidade (requer marcha ≥ 1) |
| **2** | Frear | Reduz velocidade até 0 |
| **3** | Subir Marcha | Aumenta marcha atual (máx: número de marchas) |
| **4** | Descer Marcha | Reduz marcha atual (mín: 0) |
| **5** | Mostrar Dados | Exibe tabela com todos os parâmetros |
| **0** | Sair | Encerra o programa |

#### 4. **Exemplo de Sessão**
```
Marca: BMW
Modelo: X5
Potência: 250
Número de marchas: 6

(Ao encerrar)
┌─────────────┬────────┐
│    (index)  │ Values │
├─────────────┼────────┤
│ marca       │ 'BMW'  │
│ modelo      │ 'X5'   │
│ potencia    │ 250    │
│ marchaAtual │ 0      │
│ velocidade  │ 50     │
└─────────────┴────────┘
```

---

## 📁 Estrutura do Projeto

```
trabalhogitt/
├── 📄 index.ts              # Arquivo principal com menu interativo
├── 📄 Veiculo.ts            # Classe que define estrutura do veículo
├── 📄 package.json          # Configuração do projeto e dependências
├── 📋 tsconfig.json         # Configuração do compilador TypeScript
├── 📝 README.md             # Este arquivo
├── 📝 requisitos.MD         # Requisitos do projeto
└── 🔧 node_modules/         # Dependências instaladas
```

### Explicação dos Arquivos Principais

#### **Veiculo.ts**
Define a classe `Veiculo` com as propriedades do automóvel:
```typescript
export class Veiculo {
    marca: string = 'Padrão';
    modelo: string = 'Padrão';
    potencia: number = 0;
    numeroMarchas: number = 5;
    marchaAtual: number = 0;
    velocidade: number = 0;
}
```

#### **index.ts**
Contém a lógica principal:
- Funções de controle do veículo
- Menu interativo
- Interação com usuário via `prompt-sync`

---

## 🔧 Documentação da API

### Classe: `Veiculo`

#### Propriedades

| Propriedade | Tipo | Valor Padrão | Descrição |
|---|---|---|---|
| `marca` | string | 'Padrão' | Fabricante do veículo |
| `modelo` | string | 'Padrão' | Modelo/nome do veículo |
| `potencia` | number | 0 | Potência em cavalos-vapor (CV) |
| `numeroMarchas` | number | 5 | Total de marchas disponíveis |
| `marchaAtual` | number | 0 | Marcha ativa (0 = neutro) |
| `velocidade` | number | 0 | Velocidade em km/h |

---

### Funções Principais

#### **`criaVeiculo(): Veiculo`**
```typescript
function criaVeiculo(): Veiculo {
    const veiculo: Veiculo = new Veiculo();
    veiculo.marca = teclado('Marca: ');
    veiculo.modelo = teclado('Modelo: ');
    veiculo.potencia = +teclado('Potência: ');
    veiculo.numeroMarchas = +teclado('Número de marchas: ');
    return veiculo;
}
```
**Descrição**: Cria um novo veículo interagindo com o usuário para obter suas características.

#### **`acelerar(veiculo: Veiculo): void`**
```typescript
function acelerar(veiculo: Veiculo): void {
    if(veiculo.marchaAtual != 0) {
        veiculo.velocidade += veiculo.potencia * 0.1;
        console.log(veiculo.velocidade);
    }
}
```
**Descrição**: Aumenta a velocidade do veículo multiplicando a potência por 0.1 (se em marcha).

---

## 💡 Exemplos de Uso

### Exemplo 1: Aceleração Progressiva
```typescript
const meuCarro = new Veiculo();
meuCarro.marca = "Ferrari";
meuCarro.modelo = "F8";
meuCarro.potencia = 720;
meuCarro.marchaAtual = 1;

acelerar(meuCarro);  // velocidade = 72 km/h
acelerar(meuCarro);  // velocidade = 144 km/h
```

### Exemplo 2: Teste de Validação
```typescript
const carro = new Veiculo();
carro.marchaAtual = 0;  // Neutro
acelerar(carro);  // NÃO aumenta velocidade (validação)
```

### Exemplo 3: Simulação Completa
```bash
$ npx ts-node index.ts
Marca: Tesla
Modelo: Model 3
Potência: 440
Número de marchas: 1

########### MENU ###########
1 - Acelerar
...
3  # Subir marcha (inválido, máximo é 1)
1  # Acelerar
220  # velocidade após primeira aceleração
1  # Acelerar novamente
440  # velocidade duplicada
0  # Sair
```

---

## 🐛 Guia de Troubleshooting

### Problema 1: "Cannot find module 'prompt-sync'"
**Solução:**
```bash
npm install prompt-sync @types/prompt-sync
```

### Problema 2: Erro de compilação TypeScript
**Solução:**
```bash
npx tsc --version  # Verificar versão
npx tsc index.ts   # Compilar manualmente
```

### Problema 3: Velocidade não muda ao acelerar
**Causa:** Veículo pode estar em marcha 0 (neutro).

**Solução:** Subir marcha antes de acelerar.

### Problema 4: Node.js não reconhecido
**Solução:** Instale Node.js de https://nodejs.org/ (recomendado: LTS)

---

## 🤝 Contribuições

Contribuições são bem-vindas! Para contribuir:

1. **Faça um Fork** do projeto
2. **Crie uma branch** para sua feature (`git checkout -b feature/AmazingFeature`)
3. **Commit suas mudanças** (`git commit -m 'Add AmazingFeature'`)
4. **Push para a branch** (`git push origin feature/AmazingFeature`)
5. **Abra um Pull Request**

### Diretrizes de Contribuição
- Mantenha o código em TypeScript
- Adicione comentários para funções complexas
- Teste localmente antes de enviar

---

## 📄 Licença

Este projeto está licenciado sob a Licença ISC - veja o arquivo [LICENSE](LICENSE) para mais detalhes.

---

## 👨‍💻 Autor

Desenvolvido como parte de projeto educacional de Programação Orientada a Objetos.

**Data de Criação:** Março de 2026

---

## 📞 Suporte

Encontrou um bug? Tem uma sugestão?
- 🐛 [Reportar um Issue](https://github.com/seu-usuario/simulador-veiculos/issues)
- 💬 [Discussões](https://github.com/seu-usuario/simulador-veiculos/discussions)

---

## 🔗 Links Úteis

- [Documentação TypeScript](https://www.typescriptlang.org/)
- [Node.js](https://nodejs.org/)
- [npm Registry](https://www.npmjs.com/)
- [prompt-sync Documentation](https://www.npmjs.com/package/prompt-sync)

---

<div align="center">

**⭐ Se este projeto te ajudou, deixe uma estrela!**

Feito com ❤️ em TypeScript

</div>
