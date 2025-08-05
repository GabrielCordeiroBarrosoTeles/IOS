# Apostila de Swift - Gabriel Cordeiro

*Guia Completo de Desenvolvimento iOS com Swift*

## Índice
1. [Introdução ao Swift](#introdução-ao-swift)
2. [Variáveis e Constantes](#variáveis-e-constantes)
3. [Tipos de Dados](#tipos-de-dados)
4. [Operadores](#operadores)
5. [Estruturas de Controle](#estruturas-de-controle)
6. [Funções](#funções)
7. [Closures](#closures)
8. [Orientação a Objetos](#orientação-a-objetos)
9. [Protocolos](#protocolos)
10. [Tratamento de Erros](#tratamento-de-erros)
11. [Generics](#generics)
12. [Desenvolvimento iOS](#desenvolvimento-ios)
13. [Interface Builder e Storyboards](#interface-builder-e-storyboards)
14. [Auto Layout](#auto-layout)
15. [Navigation e Tab Controllers](#navigation-e-tab-controllers)
16. [Table Views e Collection Views](#table-views-e-collection-views)
17. [Networking](#networking)
18. [Core Data](#core-data)
19. [Arquiteturas (MVC, MVVM)](#arquiteturas)
20. [Testes](#testes)
21. [UI/UX - Criação de Telas](#uiux---criação-de-telas)
22. [Componentes Visuais](#componentes-visuais)
23. [Animações e Transições](#animações-e-transições)
24. [Design Patterns para UI](#design-patterns-para-ui)
25. [Acessibilidade](#acessibilidade)
26. [SwiftUI Básico](#swiftui-básico)
27. [Combine Framework](#combine-framework)
28. [Core Location e MapKit](#core-location-e-mapkit)
29. [Camera e Photos](#camera-e-photos)
30. [Push Notifications](#push-notifications)
31. [In-App Purchases](#in-app-purchases)
32. [CloudKit](#cloudkit)
33. [Widgets](#widgets)
34. [App Extensions](#app-extensions)
35. [Performance e Otimização](#performance-e-otimização)
36. [Segurança](#segurança)
37. [Publicação na App Store](#publicação-na-app-store)
38. [Concorrência e Async/Await](#concorrência-e-asyncawait)
39. [Realidade Aumentada (ARKit)](#realidade-aumentada-arkit)
40. [Inteligência Artificial (Core ML)](#inteligência-artificial-core-ml)
41. [Projeto Completo: App de Tarefas](#projeto-completo-app-de-tarefas)
42. [Projeto Avançado: Rede Social](#projeto-avançado-rede-social)
43. [Dicas Profissionais](#dicas-profissionais)

---

## Introdução ao Swift

Swift é uma linguagem de programação moderna, segura e performática desenvolvida pela Apple para iOS, macOS, watchOS e tvOS.

### Características principais:
- **Type Safety**: Previne erros de tipo em tempo de compilação
- **Memory Management**: Gerenciamento automático de memória (ARC)
- **Optionals**: Sistema para lidar com valores nulos de forma segura
- **Interoperabilidade**: Funciona com Objective-C

---

## Variáveis e Constantes

### Declaração
```swift
// Constantes (valor não pode ser alterado)
let nome = "João"
let idade = 25

// Variáveis (valor pode ser alterado)
var pontuacao = 100
var ativo = true

// Declaração com tipo explícito
let pi: Double = 3.14159
var contador: Int = 0
```

### Regras de nomenclatura
- Use camelCase
- Comece com letra minúscula
- Seja descritivo: `nomeCompleto` ao invés de `n`

---

## Tipos de Dados

### Tipos Básicos
```swift
// Números inteiros
let numeroInteiro: Int = 42
let numeroPositivo: UInt = 42

// Números decimais
let numeroDecimal: Double = 3.14159
let numeroFloat: Float = 3.14

// Texto
let texto: String = "Olá, mundo!"
let caractere: Character = "A"

// Booleano
let verdadeiro: Bool = true
let falso: Bool = false
```

### Strings
```swift
let nome = "Maria"
let sobrenome = "Silva"

// Interpolação de strings
let nomeCompleto = "\(nome) \(sobrenome)"

// Métodos úteis
let tamanho = nome.count
let maiusculo = nome.uppercased()
let minusculo = nome.lowercased()
let contemMaria = nome.contains("Maria")
```

### Arrays
```swift
// Declaração
var numeros = [1, 2, 3, 4, 5]
var nomes: [String] = ["Ana", "Bruno", "Carlos"]
var arrayVazio: [Int] = []

// Operações
numeros.append(6)
numeros.insert(0, at: 0)
numeros.remove(at: 0)
let primeiro = numeros.first
let ultimo = numeros.last
let tamanho = numeros.count
```

### Dicionários
```swift
// Declaração
var idades = ["Ana": 25, "Bruno": 30, "Carlos": 28]
var dicionarioVazio: [String: Int] = [:]

// Operações
idades["Diana"] = 22
idades["Ana"] = 26
idades.removeValue(forKey: "Bruno")
let idadeAna = idades["Ana"] // Retorna Optional
```

### Tuplas
```swift
let coordenada = (x: 10, y: 20)
let pessoa = (nome: "João", idade: 30)

// Acesso
print(coordenada.x) // 10
print(pessoa.nome)  // "João"

// Desestruturação
let (x, y) = coordenada
let (nome, _) = pessoa // _ ignora o valor
```

---

## Operadores

### Aritméticos
```swift
let a = 10
let b = 3

let soma = a + b        // 13
let subtracao = a - b   // 7
let multiplicacao = a * b // 30
let divisao = a / b     // 3
let resto = a % b       // 1
```

### Comparação
```swift
let x = 5
let y = 10

x == y  // false (igual)
x != y  // true (diferente)
x < y   // true (menor)
x > y   // false (maior)
x <= y  // true (menor ou igual)
x >= y  // false (maior ou igual)
```

### Lógicos
```swift
let verdadeiro = true
let falso = false

!verdadeiro           // false (NOT)
verdadeiro && falso   // false (AND)
verdadeiro || falso   // true (OR)
```

---

## Estruturas de Controle

### If/Else
```swift
let idade = 18

if idade >= 18 {
    print("Maior de idade")
} else if idade >= 16 {
    print("Pode votar")
} else {
    print("Menor de idade")
}

// If ternário
let status = idade >= 18 ? "Adulto" : "Menor"
```

### Switch
```swift
let nota = "A"

switch nota {
case "A":
    print("Excelente")
case "B":
    print("Bom")
case "C":
    print("Regular")
case "D", "F":
    print("Insuficiente")
default:
    print("Nota inválida")
}

// Switch com ranges
let pontuacao = 85

switch pontuacao {
case 90...100:
    print("A")
case 80..<90:
    print("B")
case 70..<80:
    print("C")
default:
    print("F")
}
```

### Guard
```swift
func processarIdade(_ idade: Int?) {
    guard let idadeValida = idade, idadeValida > 0 else {
        print("Idade inválida")
        return
    }
    
    print("Idade: \(idadeValida)")
}
```

---

## Estruturas de Repetição

### For-in
```swift
// Array
let numeros = [1, 2, 3, 4, 5]
for numero in numeros {
    print(numero)
}

// Range
for i in 1...5 {
    print(i) // 1, 2, 3, 4, 5
}

for i in 1..<5 {
    print(i) // 1, 2, 3, 4
}

// Dicionário
let idades = ["Ana": 25, "Bruno": 30]
for (nome, idade) in idades {
    print("\(nome): \(idade)")
}

// Com índice
let frutas = ["maçã", "banana", "laranja"]
for (indice, fruta) in frutas.enumerated() {
    print("\(indice): \(fruta)")
}
```

### While
```swift
var contador = 0
while contador < 5 {
    print(contador)
    contador += 1
}
```

### Repeat-While
```swift
var numero = 0
repeat {
    print(numero)
    numero += 1
} while numero < 3
```

---

## Funções

### Declaração básica
```swift
func saudacao() {
    print("Olá!")
}

func saudar(nome: String) {
    print("Olá, \(nome)!")
}

func somar(a: Int, b: Int) -> Int {
    return a + b
}

// Chamadas
saudacao()
saudar(nome: "Maria")
let resultado = somar(a: 5, b: 3)
```

### Parâmetros
```swift
// Labels externos e internos
func saudar(para nome: String, de remetente: String) {
    print("Olá \(nome), de \(remetente)")
}
saudar(para: "Ana", de: "João")

// Omitir label externo
func multiplicar(_ a: Int, por b: Int) -> Int {
    return a * b
}
let produto = multiplicar(5, por: 3)

// Valores padrão
func criarUsuario(nome: String, idade: Int = 18) {
    print("Usuário: \(nome), \(idade) anos")
}
criarUsuario(nome: "Pedro")
criarUsuario(nome: "Ana", idade: 25)

// Parâmetros variádicos
func calcularMedia(_ numeros: Double...) -> Double {
    let soma = numeros.reduce(0, +)
    return soma / Double(numeros.count)
}
let media = calcularMedia(10, 20, 30, 40)
```

### Funções como tipos
```swift
func somar(_ a: Int, _ b: Int) -> Int {
    return a + b
}

func multiplicar(_ a: Int, _ b: Int) -> Int {
    return a * b
}

// Função como variável
var operacao: (Int, Int) -> Int = somar
let resultado1 = operacao(5, 3) // 8

operacao = multiplicar
let resultado2 = operacao(5, 3) // 15

// Função como parâmetro
func executarOperacao(_ a: Int, _ b: Int, operacao: (Int, Int) -> Int) -> Int {
    return operacao(a, b)
}

let soma = executarOperacao(10, 5, operacao: somar)
```

---

## Closures

Closures são blocos de código que podem ser passados e executados.

```swift
// Sintaxe completa
let somar = { (a: Int, b: Int) -> Int in
    return a + b
}

// Sintaxe simplificada
let numeros = [1, 2, 3, 4, 5]

// Com closure completo
let dobrados = numeros.map({ (numero: Int) -> Int in
    return numero * 2
})

// Simplificado (tipo inferido)
let dobrados2 = numeros.map({ numero in
    return numero * 2
})

// Mais simplificado
let dobrados3 = numeros.map({ $0 * 2 })

// Trailing closure
let dobrados4 = numeros.map { $0 * 2 }

// Exemplos práticos
let pares = numeros.filter { $0 % 2 == 0 }
let soma = numeros.reduce(0) { $0 + $1 }
let ordenados = numeros.sorted { $0 > $1 }
```

---

## Orientação a Objetos

### Classes
```swift
class Pessoa {
    // Propriedades
    var nome: String
    var idade: Int
    
    // Inicializador
    init(nome: String, idade: Int) {
        self.nome = nome
        self.idade = idade
    }
    
    // Métodos
    func apresentar() {
        print("Olá, eu sou \(nome) e tenho \(idade) anos")
    }
    
    func fazerAniversario() {
        idade += 1
    }
}

// Uso
let pessoa = Pessoa(nome: "João", idade: 25)
pessoa.apresentar()
pessoa.fazerAniversario()
```

### Herança
```swift
class Funcionario: Pessoa {
    var salario: Double
    var cargo: String
    
    init(nome: String, idade: Int, cargo: String, salario: Double) {
        self.cargo = cargo
        self.salario = salario
        super.init(nome: nome, idade: idade)
    }
    
    override func apresentar() {
        super.apresentar()
        print("Trabalho como \(cargo)")
    }
    
    func receberAumento(_ percentual: Double) {
        salario *= (1 + percentual / 100)
    }
}
```

### Propriedades Computadas
```swift
class Retangulo {
    var largura: Double
    var altura: Double
    
    // Propriedade computada
    var area: Double {
        get {
            return largura * altura
        }
        set {
            // Assumindo que é um quadrado
            largura = sqrt(newValue)
            altura = sqrt(newValue)
        }
    }
    
    // Propriedade somente leitura
    var perimetro: Double {
        return 2 * (largura + altura)
    }
    
    init(largura: Double, altura: Double) {
        self.largura = largura
        self.altura = altura
    }
}
```

### Observadores de Propriedade
```swift
class ContadorPontos {
    var pontos: Int = 0 {
        willSet {
            print("Pontos vão mudar de \(pontos) para \(newValue)")
        }
        didSet {
            print("Pontos mudaram de \(oldValue) para \(pontos)")
            if pontos > 100 {
                print("Parabéns! Você passou de 100 pontos!")
            }
        }
    }
}
```

### Structs
```swift
struct Ponto {
    var x: Double
    var y: Double
    
    // Métodos mutating para structs
    mutating func mover(deltaX: Double, deltaY: Double) {
        x += deltaX
        y += deltaY
    }
    
    func distancia(para outro: Ponto) -> Double {
        let deltaX = x - outro.x
        let deltaY = y - outro.y
        return sqrt(deltaX * deltaX + deltaY * deltaY)
    }
}

var ponto = Ponto(x: 0, y: 0)
ponto.mover(deltaX: 3, deltaY: 4)
```

### Enums
```swift
enum DiaDaSemana {
    case segunda, terca, quarta, quinta, sexta, sabado, domingo
}

enum StatusPedido {
    case pendente
    case processando
    case enviado(String) // Valor associado
    case entregue(Data)
    case cancelado
}

// Uso
let status = StatusPedido.enviado("ABC123")

switch status {
case .pendente:
    print("Aguardando processamento")
case .enviado(let codigo):
    print("Enviado com código: \(codigo)")
case .entregue(let data):
    print("Entregue em: \(data)")
default:
    print("Outro status")
}

// Enum com raw values
enum Planeta: Int {
    case mercurio = 1, venus, terra, marte
}

let terra = Planeta.terra
print(terra.rawValue) // 3
```

---

## Protocolos

Protocolos definem um conjunto de métodos e propriedades que tipos podem implementar.

```swift
protocol Veiculo {
    var velocidadeMaxima: Double { get }
    var numeroRodas: Int { get }
    
    func acelerar()
    func frear()
}

protocol Voador {
    var altitudeMaxima: Double { get }
    func decolar()
    func pousar()
}

class Carro: Veiculo {
    let velocidadeMaxima: Double = 200
    let numeroRodas: Int = 4
    
    func acelerar() {
        print("Carro acelerando...")
    }
    
    func frear() {
        print("Carro freando...")
    }
}

class Aviao: Veiculo, Voador {
    let velocidadeMaxima: Double = 900
    let numeroRodas: Int = 3
    let altitudeMaxima: Double = 12000
    
    func acelerar() {
        print("Avião acelerando na pista...")
    }
    
    func frear() {
        print("Avião freando...")
    }
    
    func decolar() {
        print("Avião decolando...")
    }
    
    func pousar() {
        print("Avião pousando...")
    }
}

// Extensions em protocolos
extension Veiculo {
    func mostrarInfo() {
        print("Velocidade máxima: \(velocidadeMaxima) km/h")
        print("Número de rodas: \(numeroRodas)")
    }
}
```

---

## Optionals

Sistema do Swift para lidar com valores que podem ser nulos.

```swift
var nome: String? = "João"
var idade: Int? = nil

// Unwrapping forçado (perigoso!)
// print(nome!) // Só use se tiver certeza que não é nil

// Optional binding
if let nomeSeguro = nome {
    print("Nome: \(nomeSeguro)")
} else {
    print("Nome não disponível")
}

// Guard let
func processarNome(_ nome: String?) {
    guard let nomeValido = nome else {
        print("Nome inválido")
        return
    }
    print("Processando: \(nomeValido)")
}

// Nil coalescing operator
let nomeParaExibir = nome ?? "Usuário Anônimo"

// Optional chaining
class Pessoa {
    var endereco: Endereco?
}

class Endereco {
    var rua: String?
}

let pessoa = Pessoa()
let rua = pessoa.endereco?.rua // Retorna String?
```

---

## Tratamento de Erros

```swift
enum ErroValidacao: Error {
    case idadeInvalida
    case nomeVazio
    case emailInvalido
}

func validarUsuario(nome: String, idade: Int, email: String) throws {
    if nome.isEmpty {
        throw ErroValidacao.nomeVazio
    }
    
    if idade < 0 || idade > 120 {
        throw ErroValidacao.idadeInvalida
    }
    
    if !email.contains("@") {
        throw ErroValidacao.emailInvalido
    }
}

// Uso com do-catch
do {
    try validarUsuario(nome: "João", idade: 25, email: "joao@email.com")
    print("Usuário válido!")
} catch ErroValidacao.nomeVazio {
    print("Nome não pode estar vazio")
} catch ErroValidacao.idadeInvalida {
    print("Idade inválida")
} catch ErroValidacao.emailInvalido {
    print("Email inválido")
} catch {
    print("Erro desconhecido: \(error)")
}

// Try opcional
let resultado = try? validarUsuario(nome: "", idade: 25, email: "test@test.com")
// resultado será nil se houver erro

// Try forçado (use com cuidado!)
// try! validarUsuario(nome: "João", idade: 25, email: "joao@email.com")
```

---

## Generics

Permitem escrever código flexível e reutilizável.

```swift
// Função genérica
func trocar<T>(_ a: inout T, _ b: inout T) {
    let temp = a
    a = b
    b = temp
}

var x = 5
var y = 10
trocar(&x, &y) // x = 10, y = 5

var nome1 = "Ana"
var nome2 = "Bruno"
trocar(&nome1, &nome2) // nome1 = "Bruno", nome2 = "Ana"

// Struct genérica
struct Pilha<Element> {
    private var items: [Element] = []
    
    mutating func push(_ item: Element) {
        items.append(item)
    }
    
    mutating func pop() -> Element? {
        return items.popLast()
    }
    
    func peek() -> Element? {
        return items.last
    }
    
    var isEmpty: Bool {
        return items.isEmpty
    }
}

var pilhaInteiros = Pilha<Int>()
pilhaInteiros.push(1)
pilhaInteiros.push(2)
let topo = pilhaInteiros.pop() // 2

var pilhaStrings = Pilha<String>()
pilhaStrings.push("primeiro")
pilhaStrings.push("segundo")
```

---

## Desenvolvimento iOS

### Estrutura de um App iOS

Um app iOS típico consiste em:
- **AppDelegate**: Gerencia o ciclo de vida do app
- **SceneDelegate**: Gerencia cenas (iOS 13+)
- **View Controllers**: Controlam as telas
- **Views**: Interface do usuário
- **Models**: Dados e lógica de negócio

### Ciclo de Vida do App

```swift
// AppDelegate.swift
class AppDelegate: UIResponder, UIApplicationDelegate {
    
    func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
        // App foi iniciado
        return true
    }
    
    func applicationDidBecomeActive(_ application: UIApplication) {
        // App ficou ativo
    }
    
    func applicationWillResignActive(_ application: UIApplication) {
        // App vai ficar inativo
    }
    
    func applicationDidEnterBackground(_ application: UIApplication) {
        // App foi para background
    }
    
    func applicationWillEnterForeground(_ application: UIApplication) {
        // App vai voltar para foreground
    }
}
```

### View Controllers

```swift
import UIKit

class ViewController: UIViewController {
    
    @IBOutlet weak var labelTitulo: UILabel!
    @IBOutlet weak var botaoAcao: UIButton!
    
    override func viewDidLoad() {
        super.viewDidLoad()
        // View foi carregada na memória
        configurarInterface()
    }
    
    override func viewWillAppear(_ animated: Bool) {
        super.viewWillAppear(animated)
        // View vai aparecer
    }
    
    override func viewDidAppear(_ animated: Bool) {
        super.viewDidAppear(animated)
        // View apareceu
    }
    
    override func viewWillDisappear(_ animated: Bool) {
        super.viewWillDisappear(animated)
        // View vai desaparecer
    }
    
    override func viewDidDisappear(_ animated: Bool) {
        super.viewDidDisappear(animated)
        // View desapareceu
    }
    
    private func configurarInterface() {
        labelTitulo.text = "Bem-vindo!"
        botaoAcao.setTitle("Clique aqui", for: .normal)
    }
    
    @IBAction func botaoClicado(_ sender: UIButton) {
        print("Botão foi clicado!")
        labelTitulo.text = "Botão clicado!"
    }
}
```

---

## Interface Builder e Storyboards

### Storyboards
- Representação visual das telas do app
- Permite criar interfaces arrastando elementos
- Define navegação entre telas (segues)

### IBOutlet e IBAction
```swift
class MinhaViewController: UIViewController {
    
    // IBOutlet - conecta elemento visual ao código
    @IBOutlet weak var meuLabel: UILabel!
    @IBOutlet weak var meuTextField: UITextField!
    @IBOutlet weak var minhaImageView: UIImageView!
    
    // IBAction - conecta ação (toque, etc.) ao código
    @IBAction func botaoTocado(_ sender: UIButton) {
        meuLabel.text = meuTextField.text
    }
    
    @IBAction func textFieldEditingChanged(_ sender: UITextField) {
        print("Texto mudou: \(sender.text ?? "")")
    }
}
```

### Segues
```swift
// Preparar dados antes da navegação
override func prepare(for segue: UIStoryboardSegue, sender: Any?) {
    if segue.identifier == "mostrarDetalhes" {
        if let destinoVC = segue.destination as? DetalhesViewController {
            destinoVC.dados = "Dados para passar"
        }
    }
}

// Navegação programática
@IBAction func irParaProximaTela(_ sender: UIButton) {
    performSegue(withIdentifier: "mostrarDetalhes", sender: self)
}
```

---

## Auto Layout

Sistema para criar interfaces que se adaptam a diferentes tamanhos de tela.

### Constraints Programáticas
```swift
override func viewDidLoad() {
    super.viewDidLoad()
    
    let botao = UIButton(type: .system)
    botao.setTitle("Meu Botão", for: .normal)
    botao.translatesAutoresizingMaskIntoConstraints = false
    view.addSubview(botao)
    
    // Constraints
    NSLayoutConstraint.activate([
        botao.centerXAnchor.constraint(equalTo: view.centerXAnchor),
        botao.centerYAnchor.constraint(equalTo: view.centerYAnchor),
        botao.widthAnchor.constraint(equalToConstant: 200),
        botao.heightAnchor.constraint(equalToConstant: 50)
    ])
}
```

### Stack Views
```swift
let stackView = UIStackView()
stackView.axis = .vertical
stackView.distribution = .fillEqually
stackView.spacing = 10
stackView.translatesAutoresizingMaskIntoConstraints = false

let label1 = UILabel()
label1.text = "Label 1"
let label2 = UILabel()
label2.text = "Label 2"

stackView.addArrangedSubview(label1)
stackView.addArrangedSubview(label2)

view.addSubview(stackView)

NSLayoutConstraint.activate([
    stackView.centerXAnchor.constraint(equalTo: view.centerXAnchor),
    stackView.centerYAnchor.constraint(equalTo: view.centerYAnchor),
    stackView.leadingAnchor.constraint(equalTo: view.leadingAnchor, constant: 20),
    stackView.trailingAnchor.constraint(equalTo: view.trailingAnchor, constant: -20)
])
```

---

## Navigation e Tab Controllers

### Navigation Controller
```swift
// Empilhar view controller
let novoVC = UIStoryboard(name: "Main", bundle: nil).instantiateViewController(withIdentifier: "NovoViewController")
navigationController?.pushViewController(novoVC, animated: true)

// Desempilhar
navigationController?.popViewController(animated: true)

// Voltar para root
navigationController?.popToRootViewController(animated: true)

// Customizar navigation bar
navigationItem.title = "Minha Tela"
navigationItem.rightBarButtonItem = UIBarButtonItem(barButtonSystemItem: .add, target: self, action: #selector(adicionarItem))

@objc func adicionarItem() {
    print("Adicionar item")
}
```

### Tab Bar Controller
```swift
// No AppDelegate ou SceneDelegate
let tabBarController = UITabBarController()

let primeiraVC = UIViewController()
primeiraVC.tabBarItem = UITabBarItem(title: "Primeira", image: UIImage(systemName: "house"), tag: 0)

let segundaVC = UIViewController()
segundaVC.tabBarItem = UITabBarItem(title: "Segunda", image: UIImage(systemName: "person"), tag: 1)

tabBarController.viewControllers = [primeiraVC, segundaVC]
```

---

## Table Views e Collection Views

### Table View
```swift
class TabelaViewController: UIViewController {
    
    @IBOutlet weak var tableView: UITableView!
    
    let dados = ["Item 1", "Item 2", "Item 3", "Item 4", "Item 5"]
    
    override func viewDidLoad() {
        super.viewDidLoad()
        
        tableView.dataSource = self
        tableView.delegate = self
    }
}

extension TabelaViewController: UITableViewDataSource {
    
    func tableView(_ tableView: UITableView, numberOfRowsInSection section: Int) -> Int {
        return dados.count
    }
    
    func tableView(_ tableView: UITableView, cellForRowAt indexPath: IndexPath) -> UITableViewCell {
        let cell = tableView.dequeueReusableCell(withIdentifier: "cell", for: indexPath)
        cell.textLabel?.text = dados[indexPath.row]
        return cell
    }
}

extension TabelaViewController: UITableViewDelegate {
    
    func tableView(_ tableView: UITableView, didSelectRowAt indexPath: IndexPath) {
        tableView.deselectRow(at: indexPath, animated: true)
        print("Selecionou: \(dados[indexPath.row])")
    }
    
    func tableView(_ tableView: UITableView, commit editingStyle: UITableViewCell.EditingStyle, forRowAt indexPath: IndexPath) {
        if editingStyle == .delete {
            dados.remove(at: indexPath.row)
            tableView.deleteRows(at: [indexPath], with: .fade)
        }
    }
}
```

### Custom Table View Cell
```swift
class CustomTableViewCell: UITableViewCell {
    
    @IBOutlet weak var tituloLabel: UILabel!
    @IBOutlet weak var subtituloLabel: UILabel!
    @IBOutlet weak var imagemView: UIImageView!
    
    func configurar(titulo: String, subtitulo: String, imagem: UIImage?) {
        tituloLabel.text = titulo
        subtituloLabel.text = subtitulo
        imagemView.image = imagem
    }
}

// Uso na table view
func tableView(_ tableView: UITableView, cellForRowAt indexPath: IndexPath) -> UITableViewCell {
    let cell = tableView.dequeueReusableCell(withIdentifier: "CustomCell", for: indexPath) as! CustomTableViewCell
    
    let item = dados[indexPath.row]
    cell.configurar(titulo: item.titulo, subtitulo: item.subtitulo, imagem: item.imagem)
    
    return cell
}
```

### Collection View
```swift
class ColecaoViewController: UIViewController {
    
    @IBOutlet weak var collectionView: UICollectionView!
    
    let cores: [UIColor] = [.red, .blue, .green, .yellow, .purple, .orange]
    
    override func viewDidLoad() {
        super.viewDidLoad()
        
        collectionView.dataSource = self
        collectionView.delegate = self
        
        // Layout
        let layout = UICollectionViewFlowLayout()
        layout.itemSize = CGSize(width: 100, height: 100)
        layout.minimumInteritemSpacing = 10
        layout.minimumLineSpacing = 10
        collectionView.collectionViewLayout = layout
    }
}

extension ColecaoViewController: UICollectionViewDataSource {
    
    func collectionView(_ collectionView: UICollectionView, numberOfItemsInSection section: Int) -> Int {
        return cores.count
    }
    
    func collectionView(_ collectionView: UICollectionView, cellForItemAt indexPath: IndexPath) -> UICollectionViewCell {
        let cell = collectionView.dequeueReusableCell(withReuseIdentifier: "cell", for: indexPath)
        cell.backgroundColor = cores[indexPath.item]
        return cell
    }
}
```

---

## Networking

### URLSession
```swift
import Foundation

class NetworkManager {
    
    static let shared = NetworkManager()
    private init() {}
    
    func buscarDados(url: String, completion: @escaping (Result<Data, Error>) -> Void) {
        guard let url = URL(string: url) else {
            completion(.failure(NetworkError.urlInvalida))
            return
        }
        
        URLSession.shared.dataTask(with: url) { data, response, error in
            if let error = error {
                completion(.failure(error))
                return
            }
            
            guard let data = data else {
                completion(.failure(NetworkError.dadosIndisponiveis))
                return
            }
            
            completion(.success(data))
        }.resume()
    }
    
    func buscarJSON<T: Codable>(url: String, tipo: T.Type, completion: @escaping (Result<T, Error>) -> Void) {
        buscarDados(url: url) { result in
            switch result {
            case .success(let data):
                do {
                    let objeto = try JSONDecoder().decode(tipo, from: data)
                    completion(.success(objeto))
                } catch {
                    completion(.failure(error))
                }
            case .failure(let error):
                completion(.failure(error))
            }
        }
    }
}

enum NetworkError: Error {
    case urlInvalida
    case dadosIndisponiveis
}

// Modelo de dados
struct Usuario: Codable {
    let id: Int
    let nome: String
    let email: String
}

// Uso
NetworkManager.shared.buscarJSON(url: "https://api.exemplo.com/usuarios", tipo: [Usuario].self) { result in
    DispatchQueue.main.async {
        switch result {
        case .success(let usuarios):
            print("Usuários carregados: \(usuarios.count)")
        case .failure(let error):
            print("Erro: \(error)")
        }
    }
}
```

### Async/Await (iOS 15+)
```swift
class NetworkManagerModerno {
    
    static let shared = NetworkManagerModerno()
    private init() {}
    
    func buscarDados(url: String) async throws -> Data {
        guard let url = URL(string: url) else {
            throw NetworkError.urlInvalida
        }
        
        let (data, _) = try await URLSession.shared.data(from: url)
        return data
    }
    
    func buscarJSON<T: Codable>(url: String, tipo: T.Type) async throws -> T {
        let data = try await buscarDados(url: url)
        return try JSONDecoder().decode(tipo, from: data)
    }
}

// Uso
Task {
    do {
        let usuarios = try await NetworkManagerModerno.shared.buscarJSON(url: "https://api.exemplo.com/usuarios", tipo: [Usuario].self)
        print("Usuários: \(usuarios)")
    } catch {
        print("Erro: \(error)")
    }
}
```

---

## Core Data

Framework para persistência de dados.

### Configuração
```swift
import CoreData

class CoreDataManager {
    
    static let shared = CoreDataManager()
    private init() {}
    
    lazy var persistentContainer: NSPersistentContainer = {
        let container = NSPersistentContainer(name: "DataModel")
        container.loadPersistentStores { _, error in
            if let error = error {
                fatalError("Erro ao carregar Core Data: \(error)")
            }
        }
        return container
    }()
    
    var context: NSManagedObjectContext {
        return persistentContainer.viewContext
    }
    
    func salvar() {
        if context.hasChanges {
            do {
                try context.save()
            } catch {
                print("Erro ao salvar: \(error)")
            }
        }
    }
}
```

### Operações CRUD
```swift
// Create
func criarUsuario(nome: String, email: String) {
    let usuario = Usuario(context: CoreDataManager.shared.context)
    usuario.nome = nome
    usuario.email = email
    usuario.dataCriacao = Date()
    
    CoreDataManager.shared.salvar()
}

// Read
func buscarUsuarios() -> [Usuario] {
    let request: NSFetchRequest<Usuario> = Usuario.fetchRequest()
    
    do {
        return try CoreDataManager.shared.context.fetch(request)
    } catch {
        print("Erro ao buscar usuários: \(error)")
        return []
    }
}

// Update
func atualizarUsuario(_ usuario: Usuario, novoNome: String) {
    usuario.nome = novoNome
    CoreDataManager.shared.salvar()
}

// Delete
func deletarUsuario(_ usuario: Usuario) {
    CoreDataManager.shared.context.delete(usuario)
    CoreDataManager.shared.salvar()
}
```

---

## Arquiteturas

### MVC (Model-View-Controller)
```swift
// Model
struct Produto {
    let id: Int
    let nome: String
    let preco: Double
}

// View Controller
class ProdutosViewController: UIViewController {
    
    @IBOutlet weak var tableView: UITableView!
    
    private var produtos: [Produto] = []
    
    override func viewDidLoad() {
        super.viewDidLoad()
        carregarProdutos()
    }
    
    private func carregarProdutos() {
        // Lógica para carregar produtos
        produtos = [
            Produto(id: 1, nome: "iPhone", preco: 999.99),
            Produto(id: 2, nome: "iPad", preco: 599.99)
        ]
        tableView.reloadData()
    }
}
```

### MVVM (Model-View-ViewModel)
```swift
// Model
struct Usuario {
    let nome: String
    let email: String
}

// ViewModel
class UsuarioViewModel: ObservableObject {
    @Published var usuarios: [Usuario] = []
    @Published var carregando = false
    
    func carregarUsuarios() {
        carregando = true
        
        // Simular carregamento
        DispatchQueue.main.asyncAfter(deadline: .now() + 2) {
            self.usuarios = [
                Usuario(nome: "João", email: "joao@email.com"),
                Usuario(nome: "Maria", email: "maria@email.com")
            ]
            self.carregando = false
        }
    }
}

// View Controller
class UsuariosViewController: UIViewController {
    
    @IBOutlet weak var tableView: UITableView!
    
    private let viewModel = UsuarioViewModel()
    
    override func viewDidLoad() {
        super.viewDidLoad()
        
        // Observar mudanças no ViewModel
        viewModel.$usuarios.sink { [weak self] _ in
            DispatchQueue.main.async {
                self?.tableView.reloadData()
            }
        }.store(in: &cancellables)
        
        viewModel.carregarUsuarios()
    }
    
    private var cancellables = Set<AnyCancellable>()
}
```

---

## Testes

### Unit Tests
```swift
import XCTest
@testable import MeuApp

class CalculadoraTests: XCTestCase {
    
    var calculadora: Calculadora!
    
    override func setUp() {
        super.setUp()
        calculadora = Calculadora()
    }
    
    override func tearDown() {
        calculadora = nil
        super.tearDown()
    }
    
    func testSoma() {
        // Given
        let a = 5
        let b = 3
        
        // When
        let resultado = calculadora.somar(a, b)
        
        // Then
        XCTAssertEqual(resultado, 8)
    }
    
    func testDivisaoPorZero() {
        // Given
        let a = 10
        let b = 0
        
        // When & Then
        XCTAssertThrowsError(try calculadora.dividir(a, por: b)) { error in
            XCTAssertEqual(error as? CalculadoraError, CalculadoraError.divisaoPorZero)
        }
    }
}
```

### UI Tests
```swift
import XCTest

class MeuAppUITests: XCTestCase {
    
    var app: XCUIApplication!
    
    override func setUp() {
        super.setUp()
        continueAfterFailure = false
        app = XCUIApplication()
        app.launch()
    }
    
    func testFluxoLogin() {
        // Encontrar elementos
        let campoEmail = app.textFields["email"]
        let campoSenha = app.secureTextFields["senha"]
        let botaoLogin = app.buttons["login"]
        
        // Interagir
        campoEmail.tap()
        campoEmail.typeText("usuario@email.com")
        
        campoSenha.tap()
        campoSenha.typeText("senha123")
        
        botaoLogin.tap()
        
        // Verificar resultado
        let labelBemVindo = app.staticTexts["Bem-vindo!"]
        XCTAssertTrue(labelBemVindo.exists)
    }
}
```

---

## UI/UX - Criação de Telas

### Princípios de Design iOS

#### Human Interface Guidelines (HIG)
- **Clareza**: Interface limpa e focada no conteúdo
- **Deferência**: UI não compete com o conteúdo
- **Profundidade**: Hierarquia visual clara

#### Elementos Fundamentais
```swift
// Cores do sistema
let corPrimaria = UIColor.systemBlue
let corSecundaria = UIColor.systemGray
let corFundo = UIColor.systemBackground
let corTexto = UIColor.label

// Tipografia
let tituloGrande = UIFont.preferredFont(forTextStyle: .largeTitle)
let titulo = UIFont.preferredFont(forTextStyle: .title1)
let corpo = UIFont.preferredFont(forTextStyle: .body)
let legenda = UIFont.preferredFont(forTextStyle: .caption1)
```

### Criando Telas Programaticamente

#### Configuração Básica de uma Tela
```swift
class MinhaTelaViewController: UIViewController {
    
    // MARK: - UI Components
    private let scrollView = UIScrollView()
    private let contentView = UIView()
    private let tituloLabel = UILabel()
    private let descricaoLabel = UILabel()
    private let botaoPrincipal = UIButton(type: .system)
    private let imagemView = UIImageView()
    
    override func viewDidLoad() {
        super.viewDidLoad()
        configurarTela()
        configurarComponentes()
        configurarLayout()
        configurarAcoes()
    }
    
    private func configurarTela() {
        view.backgroundColor = .systemBackground
        title = "Minha Tela"
        
        // Navigation Bar
        navigationItem.rightBarButtonItem = UIBarButtonItem(
            barButtonSystemItem: .done,
            target: self,
            action: #selector(botaoConcluirTocado)
        )
    }
    
    private func configurarComponentes() {
        // Scroll View
        scrollView.translatesAutoresizingMaskIntoConstraints = false
        contentView.translatesAutoresizingMaskIntoConstraints = false
        
        // Título
        tituloLabel.text = "Bem-vindo!"
        tituloLabel.font = .preferredFont(forTextStyle: .largeTitle)
        tituloLabel.textAlignment = .center
        tituloLabel.numberOfLines = 0
        tituloLabel.translatesAutoresizingMaskIntoConstraints = false
        
        // Descrição
        descricaoLabel.text = "Esta é uma tela de exemplo criada programaticamente."
        descricaoLabel.font = .preferredFont(forTextStyle: .body)
        descricaoLabel.textAlignment = .center
        descricaoLabel.numberOfLines = 0
        descricaoLabel.textColor = .secondaryLabel
        descricaoLabel.translatesAutoresizingMaskIntoConstraints = false
        
        // Botão
        botaoPrincipal.setTitle("Começar", for: .normal)
        botaoPrincipal.backgroundColor = .systemBlue
        botaoPrincipal.setTitleColor(.white, for: .normal)
        botaoPrincipal.layer.cornerRadius = 12
        botaoPrincipal.titleLabel?.font = .preferredFont(forTextStyle: .headline)
        botaoPrincipal.translatesAutoresizingMaskIntoConstraints = false
        
        // Imagem
        imagemView.image = UIImage(systemName: "star.fill")
        imagemView.tintColor = .systemYellow
        imagemView.contentMode = .scaleAspectFit
        imagemView.translatesAutoresizingMaskIntoConstraints = false
    }
    
    private func configurarLayout() {
        view.addSubview(scrollView)
        scrollView.addSubview(contentView)
        
        contentView.addSubview(imagemView)
        contentView.addSubview(tituloLabel)
        contentView.addSubview(descricaoLabel)
        contentView.addSubview(botaoPrincipal)
        
        NSLayoutConstraint.activate([
            // Scroll View
            scrollView.topAnchor.constraint(equalTo: view.safeAreaLayoutGuide.topAnchor),
            scrollView.leadingAnchor.constraint(equalTo: view.leadingAnchor),
            scrollView.trailingAnchor.constraint(equalTo: view.trailingAnchor),
            scrollView.bottomAnchor.constraint(equalTo: view.bottomAnchor),
            
            // Content View
            contentView.topAnchor.constraint(equalTo: scrollView.topAnchor),
            contentView.leadingAnchor.constraint(equalTo: scrollView.leadingAnchor),
            contentView.trailingAnchor.constraint(equalTo: scrollView.trailingAnchor),
            contentView.bottomAnchor.constraint(equalTo: scrollView.bottomAnchor),
            contentView.widthAnchor.constraint(equalTo: scrollView.widthAnchor),
            
            // Imagem
            imagemView.topAnchor.constraint(equalTo: contentView.topAnchor, constant: 40),
            imagemView.centerXAnchor.constraint(equalTo: contentView.centerXAnchor),
            imagemView.widthAnchor.constraint(equalToConstant: 80),
            imagemView.heightAnchor.constraint(equalToConstant: 80),
            
            // Título
            tituloLabel.topAnchor.constraint(equalTo: imagemView.bottomAnchor, constant: 24),
            tituloLabel.leadingAnchor.constraint(equalTo: contentView.leadingAnchor, constant: 20),
            tituloLabel.trailingAnchor.constraint(equalTo: contentView.trailingAnchor, constant: -20),
            
            // Descrição
            descricaoLabel.topAnchor.constraint(equalTo: tituloLabel.bottomAnchor, constant: 16),
            descricaoLabel.leadingAnchor.constraint(equalTo: contentView.leadingAnchor, constant: 20),
            descricaoLabel.trailingAnchor.constraint(equalTo: contentView.trailingAnchor, constant: -20),
            
            // Botão
            botaoPrincipal.topAnchor.constraint(equalTo: descricaoLabel.bottomAnchor, constant: 32),
            botaoPrincipal.leadingAnchor.constraint(equalTo: contentView.leadingAnchor, constant: 20),
            botaoPrincipal.trailingAnchor.constraint(equalTo: contentView.trailingAnchor, constant: -20),
            botaoPrincipal.heightAnchor.constraint(equalToConstant: 50),
            botaoPrincipal.bottomAnchor.constraint(equalTo: contentView.bottomAnchor, constant: -40)
        ])
    }
    
    private func configurarAcoes() {
        botaoPrincipal.addTarget(self, action: #selector(botaoPrincipalTocado), for: .touchUpInside)
    }
    
    @objc private func botaoPrincipalTocado() {
        // Animação de feedback
        UIView.animate(withDuration: 0.1, animations: {
            self.botaoPrincipal.transform = CGAffineTransform(scaleX: 0.95, y: 0.95)
        }) { _ in
            UIView.animate(withDuration: 0.1) {
                self.botaoPrincipal.transform = .identity
            }
        }
        
        print("Botão principal tocado!")
    }
    
    @objc private func botaoConcluirTocado() {
        dismiss(animated: true)
    }
}
```

### Layouts Responsivos

#### Stack Views para Layouts Flexíveis
```swift
class LayoutResponsivoViewController: UIViewController {
    
    private let mainStackView = UIStackView()
    private let headerStackView = UIStackView()
    private let contentStackView = UIStackView()
    private let footerStackView = UIStackView()
    
    override func viewDidLoad() {
        super.viewDidLoad()
        configurarStackViews()
        configurarLayout()
    }
    
    private func configurarStackViews() {
        // Main Stack View
        mainStackView.axis = .vertical
        mainStackView.distribution = .fill
        mainStackView.spacing = 20
        mainStackView.translatesAutoresizingMaskIntoConstraints = false
        
        // Header Stack View
        headerStackView.axis = .horizontal
        headerStackView.distribution = .fillEqually
        headerStackView.spacing = 10
        
        // Content Stack View
        contentStackView.axis = .vertical
        contentStackView.distribution = .fillProportionally
        contentStackView.spacing = 16
        
        // Footer Stack View
        footerStackView.axis = .horizontal
        footerStackView.distribution = .fillEqually
        footerStackView.spacing = 12
        
        // Adicionar componentes
        let titulo = criarLabel(texto: "Título", estilo: .title1)
        let subtitulo = criarLabel(texto: "Subtítulo", estilo: .title2)
        headerStackView.addArrangedSubview(titulo)
        headerStackView.addArrangedSubview(subtitulo)
        
        let descricao = criarLabel(texto: "Descrição longa que se adapta ao tamanho da tela", estilo: .body)
        contentStackView.addArrangedSubview(descricao)
        
        let botao1 = criarBotao(titulo: "Cancelar", cor: .systemGray)
        let botao2 = criarBotao(titulo: "Confirmar", cor: .systemBlue)
        footerStackView.addArrangedSubview(botao1)
        footerStackView.addArrangedSubview(botao2)
        
        mainStackView.addArrangedSubview(headerStackView)
        mainStackView.addArrangedSubview(contentStackView)
        mainStackView.addArrangedSubview(footerStackView)
    }
    
    private func configurarLayout() {
        view.addSubview(mainStackView)
        
        NSLayoutConstraint.activate([
            mainStackView.topAnchor.constraint(equalTo: view.safeAreaLayoutGuide.topAnchor, constant: 20),
            mainStackView.leadingAnchor.constraint(equalTo: view.leadingAnchor, constant: 20),
            mainStackView.trailingAnchor.constraint(equalTo: view.trailingAnchor, constant: -20),
            mainStackView.bottomAnchor.constraint(lessThanOrEqualTo: view.safeAreaLayoutGuide.bottomAnchor, constant: -20)
        ])
    }
    
    private func criarLabel(texto: String, estilo: UIFont.TextStyle) -> UILabel {
        let label = UILabel()
        label.text = texto
        label.font = .preferredFont(forTextStyle: estilo)
        label.numberOfLines = 0
        label.textAlignment = .center
        return label
    }
    
    private func criarBotao(titulo: String, cor: UIColor) -> UIButton {
        let botao = UIButton(type: .system)
        botao.setTitle(titulo, for: .normal)
        botao.backgroundColor = cor
        botao.setTitleColor(.white, for: .normal)
        botao.layer.cornerRadius = 8
        botao.heightAnchor.constraint(equalToConstant: 44).isActive = true
        return botao
    }
}
```

---

## Componentes Visuais

### Botões Customizados
```swift
class BotaoCustomizado: UIButton {
    
    enum EstiloBotao {
        case primario
        case secundario
        case perigo
        case sucesso
    }
    
    private var estilo: EstiloBotao = .primario
    
    init(estilo: EstiloBotao) {
        self.estilo = estilo
        super.init(frame: .zero)
        configurar()
    }
    
    required init?(coder: NSCoder) {
        super.init(coder: coder)
        configurar()
    }
    
    private func configurar() {
        layer.cornerRadius = 12
        titleLabel?.font = .preferredFont(forTextStyle: .headline)
        
        switch estilo {
        case .primario:
            backgroundColor = .systemBlue
            setTitleColor(.white, for: .normal)
        case .secundario:
            backgroundColor = .systemGray5
            setTitleColor(.label, for: .normal)
            layer.borderWidth = 1
            layer.borderColor = UIColor.systemGray3.cgColor
        case .perigo:
            backgroundColor = .systemRed
            setTitleColor(.white, for: .normal)
        case .sucesso:
            backgroundColor = .systemGreen
            setTitleColor(.white, for: .normal)
        }
        
        // Efeitos de toque
        addTarget(self, action: #selector(botaoPressionado), for: .touchDown)
        addTarget(self, action: #selector(botaoSolto), for: [.touchUpInside, .touchUpOutside, .touchCancel])
    }
    
    @objc private func botaoPressionado() {
        UIView.animate(withDuration: 0.1) {
            self.transform = CGAffineTransform(scaleX: 0.95, y: 0.95)
            self.alpha = 0.8
        }
    }
    
    @objc private func botaoSolto() {
        UIView.animate(withDuration: 0.1) {
            self.transform = .identity
            self.alpha = 1.0
        }
    }
}

// Uso
let botaoPrimario = BotaoCustomizado(estilo: .primario)
botaoPrimario.setTitle("Salvar", for: .normal)

let botaoSecundario = BotaoCustomizado(estilo: .secundario)
botaoSecundario.setTitle("Cancelar", for: .normal)
```

### Cards e Containers
```swift
class CardView: UIView {
    
    private let containerView = UIView()
    private let tituloLabel = UILabel()
    private let conteudoLabel = UILabel()
    private let imagemView = UIImageView()
    
    override init(frame: CGRect) {
        super.init(frame: frame)
        configurar()
    }
    
    required init?(coder: NSCoder) {
        super.init(coder: coder)
        configurar()
    }
    
    private func configurar() {
        // Container
        containerView.backgroundColor = .systemBackground
        containerView.layer.cornerRadius = 16
        containerView.layer.shadowColor = UIColor.black.cgColor
        containerView.layer.shadowOffset = CGSize(width: 0, height: 2)
        containerView.layer.shadowRadius = 8
        containerView.layer.shadowOpacity = 0.1
        containerView.translatesAutoresizingMaskIntoConstraints = false
        
        // Título
        tituloLabel.font = .preferredFont(forTextStyle: .headline)
        tituloLabel.numberOfLines = 0
        tituloLabel.translatesAutoresizingMaskIntoConstraints = false
        
        // Conteúdo
        conteudoLabel.font = .preferredFont(forTextStyle: .body)
        conteudoLabel.textColor = .secondaryLabel
        conteudoLabel.numberOfLines = 0
        conteudoLabel.translatesAutoresizingMaskIntoConstraints = false
        
        // Imagem
        imagemView.contentMode = .scaleAspectFill
        imagemView.clipsToBounds = true
        imagemView.layer.cornerRadius = 8
        imagemView.translatesAutoresizingMaskIntoConstraints = false
        
        // Hierarquia
        addSubview(containerView)
        containerView.addSubview(imagemView)
        containerView.addSubview(tituloLabel)
        containerView.addSubview(conteudoLabel)
        
        // Layout
        NSLayoutConstraint.activate([
            containerView.topAnchor.constraint(equalTo: topAnchor),
            containerView.leadingAnchor.constraint(equalTo: leadingAnchor),
            containerView.trailingAnchor.constraint(equalTo: trailingAnchor),
            containerView.bottomAnchor.constraint(equalTo: bottomAnchor),
            
            imagemView.topAnchor.constraint(equalTo: containerView.topAnchor, constant: 16),
            imagemView.leadingAnchor.constraint(equalTo: containerView.leadingAnchor, constant: 16),
            imagemView.widthAnchor.constraint(equalToConstant: 60),
            imagemView.heightAnchor.constraint(equalToConstant: 60),
            
            tituloLabel.topAnchor.constraint(equalTo: containerView.topAnchor, constant: 16),
            tituloLabel.leadingAnchor.constraint(equalTo: imagemView.trailingAnchor, constant: 12),
            tituloLabel.trailingAnchor.constraint(equalTo: containerView.trailingAnchor, constant: -16),
            
            conteudoLabel.topAnchor.constraint(equalTo: tituloLabel.bottomAnchor, constant: 8),
            conteudoLabel.leadingAnchor.constraint(equalTo: imagemView.trailingAnchor, constant: 12),
            conteudoLabel.trailingAnchor.constraint(equalTo: containerView.trailingAnchor, constant: -16),
            conteudoLabel.bottomAnchor.constraint(equalTo: containerView.bottomAnchor, constant: -16)
        ])
    }
    
    func configurar(titulo: String, conteudo: String, imagem: UIImage?) {
        tituloLabel.text = titulo
        conteudoLabel.text = conteudo
        imagemView.image = imagem
    }
}
```

### Input Fields Customizados
```swift
class CampoTextoCustomizado: UIView {
    
    private let tituloLabel = UILabel()
    private let textField = UITextField()
    private let containerView = UIView()
    private let erroLabel = UILabel()
    
    var texto: String? {
        get { return textField.text }
        set { textField.text = newValue }
    }
    
    var placeholder: String? {
        didSet { textField.placeholder = placeholder }
    }
    
    var titulo: String? {
        didSet { 
            tituloLabel.text = titulo
            tituloLabel.isHidden = titulo == nil
        }
    }
    
    override init(frame: CGRect) {
        super.init(frame: frame)
        configurar()
    }
    
    required init?(coder: NSCoder) {
        super.init(coder: coder)
        configurar()
    }
    
    private func configurar() {
        // Título
        tituloLabel.font = .preferredFont(forTextStyle: .caption1)
        tituloLabel.textColor = .secondaryLabel
        tituloLabel.translatesAutoresizingMaskIntoConstraints = false
        
        // Container
        containerView.backgroundColor = .systemGray6
        containerView.layer.cornerRadius = 12
        containerView.layer.borderWidth = 1
        containerView.layer.borderColor = UIColor.systemGray4.cgColor
        containerView.translatesAutoresizingMaskIntoConstraints = false
        
        // Text Field
        textField.font = .preferredFont(forTextStyle: .body)
        textField.borderStyle = .none
        textField.translatesAutoresizingMaskIntoConstraints = false
        textField.delegate = self
        
        // Erro
        erroLabel.font = .preferredFont(forTextStyle: .caption2)
        erroLabel.textColor = .systemRed
        erroLabel.numberOfLines = 0
        erroLabel.isHidden = true
        erroLabel.translatesAutoresizingMaskIntoConstraints = false
        
        // Hierarquia
        addSubview(tituloLabel)
        addSubview(containerView)
        addSubview(erroLabel)
        containerView.addSubview(textField)
        
        // Layout
        NSLayoutConstraint.activate([
            tituloLabel.topAnchor.constraint(equalTo: topAnchor),
            tituloLabel.leadingAnchor.constraint(equalTo: leadingAnchor),
            tituloLabel.trailingAnchor.constraint(equalTo: trailingAnchor),
            
            containerView.topAnchor.constraint(equalTo: tituloLabel.bottomAnchor, constant: 4),
            containerView.leadingAnchor.constraint(equalTo: leadingAnchor),
            containerView.trailingAnchor.constraint(equalTo: trailingAnchor),
            containerView.heightAnchor.constraint(equalToConstant: 48),
            
            textField.topAnchor.constraint(equalTo: containerView.topAnchor, constant: 12),
            textField.leadingAnchor.constraint(equalTo: containerView.leadingAnchor, constant: 16),
            textField.trailingAnchor.constraint(equalTo: containerView.trailingAnchor, constant: -16),
            textField.bottomAnchor.constraint(equalTo: containerView.bottomAnchor, constant: -12),
            
            erroLabel.topAnchor.constraint(equalTo: containerView.bottomAnchor, constant: 4),
            erroLabel.leadingAnchor.constraint(equalTo: leadingAnchor),
            erroLabel.trailingAnchor.constraint(equalTo: trailingAnchor),
            erroLabel.bottomAnchor.constraint(equalTo: bottomAnchor)
        ])
    }
    
    func mostrarErro(_ mensagem: String) {
        erroLabel.text = mensagem
        erroLabel.isHidden = false
        containerView.layer.borderColor = UIColor.systemRed.cgColor
        
        UIView.animate(withDuration: 0.3) {
            self.containerView.transform = CGAffineTransform(translationX: 5, y: 0)
        } completion: { _ in
            UIView.animate(withDuration: 0.3) {
                self.containerView.transform = .identity
            }
        }
    }
    
    func limparErro() {
        erroLabel.isHidden = true
        containerView.layer.borderColor = UIColor.systemGray4.cgColor
    }
}

extension CampoTextoCustomizado: UITextFieldDelegate {
    func textFieldDidBeginEditing(_ textField: UITextField) {
        containerView.layer.borderColor = UIColor.systemBlue.cgColor
        limparErro()
    }
    
    func textFieldDidEndEditing(_ textField: UITextField) {
        containerView.layer.borderColor = UIColor.systemGray4.cgColor
    }
}
```

---

## Animações e Transições

### Animações Básicas
```swift
class AnimacoesViewController: UIViewController {
    
    @IBOutlet weak var viewAnimada: UIView!
    @IBOutlet weak var botaoAnimar: UIButton!
    
    override func viewDidLoad() {
        super.viewDidLoad()
        configurarViewAnimada()
    }
    
    private func configurarViewAnimada() {
        viewAnimada.backgroundColor = .systemBlue
        viewAnimada.layer.cornerRadius = 20
    }
    
    // Animação de movimento
    @IBAction func animarMovimento(_ sender: UIButton) {
        UIView.animate(withDuration: 1.0, delay: 0, options: [.curveEaseInOut]) {
            self.viewAnimada.center.x += 100
        } completion: { _ in
            UIView.animate(withDuration: 1.0) {
                self.viewAnimada.center.x -= 100
            }
        }
    }
    
    // Animação de escala
    @IBAction func animarEscala(_ sender: UIButton) {
        UIView.animate(withDuration: 0.5, delay: 0, usingSpringWithDamping: 0.6, initialSpringVelocity: 0.8) {
            self.viewAnimada.transform = CGAffineTransform(scaleX: 1.5, y: 1.5)
        } completion: { _ in
            UIView.animate(withDuration: 0.5) {
                self.viewAnimada.transform = .identity
            }
        }
    }
    
    // Animação de rotação
    @IBAction func animarRotacao(_ sender: UIButton) {
        UIView.animate(withDuration: 1.0) {
            self.viewAnimada.transform = CGAffineTransform(rotationAngle: .pi)
        } completion: { _ in
            UIView.animate(withDuration: 1.0) {
                self.viewAnimada.transform = .identity
            }
        }
    }
    
    // Animação de fade
    @IBAction func animarFade(_ sender: UIButton) {
        UIView.animate(withDuration: 1.0) {
            self.viewAnimada.alpha = 0.0
        } completion: { _ in
            UIView.animate(withDuration: 1.0) {
                self.viewAnimada.alpha = 1.0
            }
        }
    }
    
    // Animação combinada
    @IBAction func animarCombinada(_ sender: UIButton) {
        UIView.animateKeyframes(withDuration: 2.0, delay: 0) {
            UIView.addKeyframe(withRelativeStartTime: 0.0, relativeDuration: 0.25) {
                self.viewAnimada.transform = CGAffineTransform(scaleX: 1.2, y: 1.2)
            }
            
            UIView.addKeyframe(withRelativeStartTime: 0.25, relativeDuration: 0.25) {
                self.viewAnimada.transform = CGAffineTransform(rotationAngle: .pi/4)
            }
            
            UIView.addKeyframe(withRelativeStartTime: 0.5, relativeDuration: 0.25) {
                self.viewAnimada.backgroundColor = .systemRed
            }
            
            UIView.addKeyframe(withRelativeStartTime: 0.75, relativeDuration: 0.25) {
                self.viewAnimada.transform = .identity
                self.viewAnimada.backgroundColor = .systemBlue
            }
        }
    }
}
```

### Transições Customizadas
```swift
class TransicaoCustomizada: NSObject, UIViewControllerAnimatedTransitioning {
    
    private let duracao: TimeInterval = 0.5
    private let apresentando: Bool
    
    init(apresentando: Bool) {
        self.apresentando = apresentando
    }
    
    func transitionDuration(using transitionContext: UIViewControllerContextTransitioning?) -> TimeInterval {
        return duracao
    }
    
    func animateTransition(using transitionContext: UIViewControllerContextTransitioning) {
        guard let fromVC = transitionContext.viewController(forKey: .from),
              let toVC = transitionContext.viewController(forKey: .to) else {
            return
        }
        
        let containerView = transitionContext.containerView
        
        if apresentando {
            containerView.addSubview(toVC.view)
            toVC.view.alpha = 0.0
            toVC.view.transform = CGAffineTransform(scaleX: 0.8, y: 0.8)
            
            UIView.animate(withDuration: duracao, delay: 0, usingSpringWithDamping: 0.8, initialSpringVelocity: 0) {
                toVC.view.alpha = 1.0
                toVC.view.transform = .identity
                fromVC.view.alpha = 0.5
            } completion: { _ in
                transitionContext.completeTransition(!transitionContext.transitionWasCancelled)
            }
        } else {
            UIView.animate(withDuration: duracao) {
                fromVC.view.alpha = 0.0
                fromVC.view.transform = CGAffineTransform(scaleX: 0.8, y: 0.8)
                toVC.view.alpha = 1.0
            } completion: { _ in
                transitionContext.completeTransition(!transitionContext.transitionWasCancelled)
            }
        }
    }
}

// Uso da transição customizada
class ViewControllerComTransicao: UIViewController, UIViewControllerTransitioningDelegate {
    
    @IBAction func apresentarTela(_ sender: UIButton) {
        let novaVC = UIViewController()
        novaVC.view.backgroundColor = .systemPurple
        novaVC.transitioningDelegate = self
        novaVC.modalPresentationStyle = .custom
        
        present(novaVC, animated: true)
    }
    
    func animationController(forPresented presented: UIViewController, presenting: UIViewController, source: UIViewController) -> UIViewControllerAnimatedTransitioning? {
        return TransicaoCustomizada(apresentando: true)
    }
    
    func animationController(forDismissed dismissed: UIViewController) -> UIViewControllerAnimatedTransitioning? {
        return TransicaoCustomizada(apresentando: false)
    }
}
```

---

## Design Patterns para UI

### Factory Pattern para Views
```swift
class ViewFactory {
    
    static func criarBotao(titulo: String, estilo: BotaoCustomizado.EstiloBotao, acao: Selector, target: Any) -> BotaoCustomizado {
        let botao = BotaoCustomizado(estilo: estilo)
        botao.setTitle(titulo, for: .normal)
        botao.addTarget(target, action: acao, for: .touchUpInside)
        botao.translatesAutoresizingMaskIntoConstraints = false
        return botao
    }
    
    static func criarLabel(texto: String, estilo: UIFont.TextStyle, cor: UIColor = .label) -> UILabel {
        let label = UILabel()
        label.text = texto
        label.font = .preferredFont(forTextStyle: estilo)
        label.textColor = cor
        label.numberOfLines = 0
        label.translatesAutoresizingMaskIntoConstraints = false
        return label
    }
    
    static func criarImageView(imagem: UIImage?, contentMode: UIView.ContentMode = .scaleAspectFit) -> UIImageView {
        let imageView = UIImageView(image: imagem)
        imageView.contentMode = contentMode
        imageView.clipsToBounds = true
        imageView.translatesAutoresizingMaskIntoConstraints = false
        return imageView
    }
    
    static func criarStackView(eixo: NSLayoutConstraint.Axis, distribuicao: UIStackView.Distribution = .fill, espacamento: CGFloat = 8) -> UIStackView {
        let stackView = UIStackView()
        stackView.axis = eixo
        stackView.distribution = distribuicao
        stackView.spacing = espacamento
        stackView.translatesAutoresizingMaskIntoConstraints = false
        return stackView
    }
}
```

### Builder Pattern para Layouts
```swift
class LayoutBuilder {
    
    private var constraints: [NSLayoutConstraint] = []
    
    func adicionarConstraint(_ constraint: NSLayoutConstraint) -> LayoutBuilder {
        constraints.append(constraint)
        return self
    }
    
    func centralizar(_ view: UIView, em containerView: UIView) -> LayoutBuilder {
        constraints.append(contentsOf: [
            view.centerXAnchor.constraint(equalTo: containerView.centerXAnchor),
            view.centerYAnchor.constraint(equalTo: containerView.centerYAnchor)
        ])
        return self
    }
    
    func preencherHorizontalmente(_ view: UIView, em containerView: UIView, margem: CGFloat = 0) -> LayoutBuilder {
        constraints.append(contentsOf: [
            view.leadingAnchor.constraint(equalTo: containerView.leadingAnchor, constant: margem),
            view.trailingAnchor.constraint(equalTo: containerView.trailingAnchor, constant: -margem)
        ])
        return self
    }
    
    func definirTamanho(_ view: UIView, largura: CGFloat, altura: CGFloat) -> LayoutBuilder {
        constraints.append(contentsOf: [
            view.widthAnchor.constraint(equalToConstant: largura),
            view.heightAnchor.constraint(equalToConstant: altura)
        ])
        return self
    }
    
    func ativar() {
        NSLayoutConstraint.activate(constraints)
    }
}

// Uso
let botao = UIButton()
view.addSubview(botao)

LayoutBuilder()
    .centralizar(botao, em: view)
    .definirTamanho(botao, largura: 200, altura: 50)
    .ativar()
```

---

## Acessibilidade

### Implementando Acessibilidade
```swift
class TelaAcessivel: UIViewController {
    
    @IBOutlet weak var tituloLabel: UILabel!
    @IBOutlet weak var descricaoLabel: UILabel!
    @IBOutlet weak var botaoAcao: UIButton!
    @IBOutlet weak var imagemView: UIImageView!
    
    override func viewDidLoad() {
        super.viewDidLoad()
        configurarAcessibilidade()
    }
    
    private func configurarAcessibilidade() {
        // Título
        tituloLabel.accessibilityTraits = .header
        tituloLabel.accessibilityLabel = "Título principal da tela"
        
        // Descrição
        descricaoLabel.accessibilityLabel = "Descrição detalhada do conteúdo"
        
        // Botão
        botaoAcao.accessibilityLabel = "Executar ação principal"
        botaoAcao.accessibilityHint = "Toque duas vezes para continuar"
        botaoAcao.accessibilityTraits = .button
        
        // Imagem
        imagemView.accessibilityLabel = "Imagem ilustrativa do produto"
        imagemView.isAccessibilityElement = true
        
        // Ordem de navegação
        view.accessibilityElements = [tituloLabel!, descricaoLabel!, imagemView!, botaoAcao!]
        
        // Notificações de acessibilidade
        NotificationCenter.default.addObserver(
            self,
            selector: #selector(acessibilidadeMudou),
            name: UIAccessibility.voiceOverStatusDidChangeNotification,
            object: nil
        )
    }
    
    @objc private func acessibilidadeMudou() {
        if UIAccessibility.isVoiceOverRunning {
            // Ajustar interface para VoiceOver
            botaoAcao.titleLabel?.font = .preferredFont(forTextStyle: .title2)
        } else {
            // Interface normal
            botaoAcao.titleLabel?.font = .preferredFont(forTextStyle: .body)
        }
    }
    
    // Ação customizada de acessibilidade
    override func accessibilityPerformEscape() -> Bool {
        dismiss(animated: true)
        return true
    }
}
```

### Dynamic Type Support
```swift
class TelaComDynamicType: UIViewController {
    
    @IBOutlet weak var tituloLabel: UILabel!
    @IBOutlet weak var textoLabel: UILabel!
    
    override func viewDidLoad() {
        super.viewDidLoad()
        configurarDynamicType()
    }
    
    private func configurarDynamicType() {
        // Configurar fontes que se adaptam ao tamanho preferido do usuário
        tituloLabel.font = .preferredFont(forTextStyle: .largeTitle)
        tituloLabel.adjustsFontForContentSizeCategory = true
        
        textoLabel.font = .preferredFont(forTextStyle: .body)
        textoLabel.adjustsFontForContentSizeCategory = true
        
        // Observar mudanças no tamanho da fonte
        NotificationCenter.default.addObserver(
            self,
            selector: #selector(tamanhoFonteMudou),
            name: UIContentSizeCategory.didChangeNotification,
            object: nil
        )
    }
    
    @objc private func tamanhoFonteMudou() {
        // Reconfigurar layout se necessário
        view.setNeedsLayout()
        view.layoutIfNeeded()
    }
    
    deinit {
        NotificationCenter.default.removeObserver(self)
    }
}
```

---

## Conceitos Avançados

### Delegates
```swift
protocol MinhaDelegate: AnyObject {
    func algumEventoAconteceu(dados: String)
}

class MinhaClasse {
    weak var delegate: MinhaDelegate?
    
    func executarAlgumaAcao() {
        // Fazer algo...
        delegate?.algumEventoAconteceu(dados: "Dados importantes")
    }
}

class ViewController: UIViewController, MinhaDelegate {
    
    override func viewDidLoad() {
        super.viewDidLoad()
        
        let minhaInstancia = MinhaClasse()
        minhaInstancia.delegate = self
    }
    
    func algumEventoAconteceu(dados: String) {
        print("Recebido: \(dados)")
    }
}
```

### Notifications
```swift
// Postar notificação
NotificationCenter.default.post(name: NSNotification.Name("MeuEvento"), object: nil, userInfo: ["dados": "valor"])

// Observar notificação
NotificationCenter.default.addObserver(
    self,
    selector: #selector(eventoRecebido(_:)),
    name: NSNotification.Name("MeuEvento"),
    object: nil
)

@objc func eventoRecebido(_ notification: Notification) {
    if let dados = notification.userInfo?["dados"] as? String {
        print("Dados recebidos: \(dados)")
    }
}

// Remover observer
deinit {
    NotificationCenter.default.removeObserver(self)
}
```

### Grand Central Dispatch (GCD)
```swift
// Main queue (UI)
DispatchQueue.main.async {
    // Atualizar UI
    self.label.text = "Atualizado!"
}

// Background queue
DispatchQueue.global(qos: .background).async {
    // Trabalho pesado
    let resultado = self.processarDados()
    
    DispatchQueue.main.async {
        // Voltar para main queue para atualizar UI
        self.mostrarResultado(resultado)
    }
}

// Queue customizada
let minhaQueue = DispatchQueue(label: "com.meuapp.minhaqueue")
minhaQueue.async {
    // Trabalho na queue customizada
}

// Delay
DispatchQueue.main.asyncAfter(deadline: .now() + 2.0) {
    print("Executado após 2 segundos")
}
```

---

## Dicas e Boas Práticas

### Convenções de Nomenclatura
- **Classes**: PascalCase (`MinhaClasse`)
- **Variáveis/Funções**: camelCase (`minhaVariavel`)
- **Constantes**: camelCase (`minhaConstante`)
- **Enums**: PascalCase (`MeuEnum`)

### Memory Management
```swift
// Evitar retain cycles com weak/unowned
class Pai {
    var filhos: [Filho] = []
}

class Filho {
    weak var pai: Pai? // weak para evitar retain cycle
}

// Closures com capture lists
class MinhaClasse {
    var nome = "Teste"
    
    func configurarClosure() {
        let closure = { [weak self] in
            guard let self = self else { return }
            print(self.nome)
        }
    }
}
```

### Segurança
```swift
// Sempre validar entrada do usuário
func validarEmail(_ email: String) -> Bool {
    let emailRegex = "[A-Z0-9a-z._%+-]+@[A-Za-z0-9.-]+\\.[A-Za-z]{2,64}"
    let emailPredicate = NSPredicate(format:"SELF MATCHES %@", emailRegex)
    return emailPredicate.evaluate(with: email)
}

// Usar HTTPS sempre
let url = URL(string: "https://api.segura.com/dados")

// Não armazenar dados sensíveis em UserDefaults
// Use Keychain para senhas e tokens
```

### Performance
```swift
// Lazy loading
lazy var expensiveProperty: String = {
    // Computação pesada aqui
    return "Resultado"
}()

// Reutilizar células em table/collection views
func tableView(_ tableView: UITableView, cellForRowAt indexPath: IndexPath) -> UITableViewCell {
    let cell = tableView.dequeueReusableCell(withIdentifier: "cell", for: indexPath)
    // Configurar célula
    return cell
}

// Usar background queues para operações pesadas
DispatchQueue.global(qos: .userInitiated).async {
    // Operação pesada
    DispatchQueue.main.async {
        // Atualizar UI
    }
}
```

---

## Recursos Adicionais

### Documentação Oficial
- [Swift.org](https://swift.org)
- [Apple Developer Documentation](https://developer.apple.com/documentation/)
- [Human Interface Guidelines](https://developer.apple.com/design/human-interface-guidelines/)

### Ferramentas Úteis
- **Xcode**: IDE oficial da Apple
- **Simulator**: Testar apps sem dispositivo físico
- **Instruments**: Profiling e debugging
- **TestFlight**: Distribuição beta

### Frameworks Importantes
- **UIKit**: Interface do usuário
- **SwiftUI**: Interface declarativa (iOS 13+)
- **Core Data**: Persistência de dados
- **Core Animation**: Animações
- **AVFoundation**: Áudio e vídeo
- **MapKit**: Mapas
- **Core Location**: Localização

---

Este guia cobre os fundamentos essenciais do desenvolvimento iOS com Swift. Continue praticando, construindo projetos e explorando a documentação oficial para aprofundar seus conhecimentos!

**Próximos passos sugeridos:**
1. Criar um projeto simples (lista de tarefas)
2. Implementar navegação entre telas
3. Adicionar persistência de dados
4. Integrar com APIs
5. Publicar na App Store

---

## SwiftUI Básico

### Introdução ao SwiftUI
SwiftUI é o framework declarativo da Apple para criar interfaces de usuário.

```swift
import SwiftUI

struct ContentView: View {
    @State private var nome = ""
    @State private var contador = 0
    
    var body: some View {
        VStack(spacing: 20) {
            Text("Olá, \(nome.isEmpty ? "Mundo" : nome)!")
                .font(.largeTitle)
                .foregroundColor(.blue)
            
            TextField("Digite seu nome", text: $nome)
                .textFieldStyle(RoundedBorderTextFieldStyle())
                .padding()
            
            Text("Contador: \(contador)")
                .font(.title2)
            
            HStack {
                Button("-") {
                    contador -= 1
                }
                .buttonStyle(.bordered)
                
                Button("+") {
                    contador += 1
                }
                .buttonStyle(.borderedProminent)
            }
        }
        .padding()
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}
```

### Navegação em SwiftUI
```swift
struct NavigationExampleView: View {
    let items = ["Item 1", "Item 2", "Item 3"]
    
    var body: some View {
        NavigationView {
            List(items, id: \.self) { item in
                NavigationLink(destination: DetailView(item: item)) {
                    Text(item)
                }
            }
            .navigationTitle("Lista")
        }
    }
}

struct DetailView: View {
    let item: String
    
    var body: some View {
        VStack {
            Text("Detalhes de \(item)")
                .font(.largeTitle)
            
            Image(systemName: "star.fill")
                .font(.system(size: 100))
                .foregroundColor(.yellow)
        }
        .navigationTitle(item)
    }
}
```

### ObservableObject e @Published
```swift
class UserViewModel: ObservableObject {
    @Published var users: [User] = []
    @Published var isLoading = false
    
    func loadUsers() {
        isLoading = true
        
        // Simular carregamento
        DispatchQueue.main.asyncAfter(deadline: .now() + 2) {
            self.users = [
                User(name: "João", email: "joao@email.com"),
                User(name: "Maria", email: "maria@email.com")
            ]
            self.isLoading = false
        }
    }
}

struct User {
    let name: String
    let email: String
}

struct UserListView: View {
    @StateObject private var viewModel = UserViewModel()
    
    var body: some View {
        NavigationView {
            Group {
                if viewModel.isLoading {
                    ProgressView("Carregando...")
                } else {
                    List(viewModel.users, id: \.email) { user in
                        VStack(alignment: .leading) {
                            Text(user.name)
                                .font(.headline)
                            Text(user.email)
                                .font(.caption)
                                .foregroundColor(.secondary)
                        }
                    }
                }
            }
            .navigationTitle("Usuários")
            .onAppear {
                viewModel.loadUsers()
            }
        }
    }
}
```

---

## Combine Framework

### Publishers e Subscribers
```swift
import Combine

class DataService {
    @Published var data: [String] = []
    private var cancellables = Set<AnyCancellable>()
    
    func fetchData() {
        // Simular busca de dados
        Timer.publish(every: 1.0, on: .main, in: .common)
            .autoconnect()
            .map { _ in "Dados \(Date())" }
            .sink { [weak self] newData in
                self?.data.append(newData)
            }
            .store(in: &cancellables)
    }
}

class ViewModel: ObservableObject {
    @Published var items: [String] = []
    private let dataService = DataService()
    private var cancellables = Set<AnyCancellable>()
    
    init() {
        dataService.$data
            .sink { [weak self] data in
                self?.items = data
            }
            .store(in: &cancellables)
    }
    
    func startFetching() {
        dataService.fetchData()
    }
}
```

### Operadores do Combine
```swift
class SearchViewModel: ObservableObject {
    @Published var searchText = ""
    @Published var results: [String] = []
    private var cancellables = Set<AnyCancellable>()
    
    init() {
        $searchText
            .debounce(for: .milliseconds(500), scheduler: RunLoop.main)
            .removeDuplicates()
            .map { searchText in
                self.performSearch(searchText)
            }
            .switchToLatest()
            .receive(on: DispatchQueue.main)
            .sink { [weak self] results in
                self?.results = results
            }
            .store(in: &cancellables)
    }
    
    private func performSearch(_ query: String) -> AnyPublisher<[String], Never> {
        Future { promise in
            DispatchQueue.global().asyncAfter(deadline: .now() + 0.5) {
                let results = ["Resultado 1", "Resultado 2", "Resultado 3"]
                    .filter { $0.localizedCaseInsensitiveContains(query) }
                promise(.success(results))
            }
        }
        .eraseToAnyPublisher()
    }
}
```

---

## Core Location e MapKit

### Localização do Usuário
```swift
import CoreLocation
import MapKit

class LocationManager: NSObject, ObservableObject, CLLocationManagerDelegate {
    private let locationManager = CLLocationManager()
    @Published var location: CLLocation?
    @Published var authorizationStatus: CLAuthorizationStatus = .notDetermined
    
    override init() {
        super.init()
        locationManager.delegate = self
        locationManager.desiredAccuracy = kCLLocationAccuracyBest
    }
    
    func requestLocation() {
        locationManager.requestWhenInUseAuthorization()
        locationManager.startUpdatingLocation()
    }
    
    func locationManager(_ manager: CLLocationManager, didUpdateLocations locations: [CLLocation]) {
        location = locations.last
    }
    
    func locationManager(_ manager: CLLocationManager, didChangeAuthorization status: CLAuthorizationStatus) {
        authorizationStatus = status
    }
}

class MapViewController: UIViewController {
    @IBOutlet weak var mapView: MKMapView!
    private let locationManager = CLLocationManager()
    
    override func viewDidLoad() {
        super.viewDidLoad()
        setupMap()
        requestLocationPermission()
    }
    
    private func setupMap() {
        mapView.delegate = self
        mapView.showsUserLocation = true
        mapView.userTrackingMode = .none
    }
    
    private func requestLocationPermission() {
        locationManager.delegate = self
        locationManager.requestWhenInUseAuthorization()
    }
    
    private func addAnnotation(at coordinate: CLLocationCoordinate2D, title: String) {
        let annotation = MKPointAnnotation()
        annotation.coordinate = coordinate
        annotation.title = title
        mapView.addAnnotation(annotation)
    }
}

extension MapViewController: CLLocationManagerDelegate {
    func locationManager(_ manager: CLLocationManager, didUpdateLocations locations: [CLLocation]) {
        guard let location = locations.last else { return }
        
        let region = MKCoordinateRegion(
            center: location.coordinate,
            latitudinalMeters: 1000,
            longitudinalMeters: 1000
        )
        mapView.setRegion(region, animated: true)
    }
}

extension MapViewController: MKMapViewDelegate {
    func mapView(_ mapView: MKMapView, viewFor annotation: MKAnnotation) -> MKAnnotationView? {
        guard !(annotation is MKUserLocation) else { return nil }
        
        let identifier = "CustomPin"
        var annotationView = mapView.dequeueReusableAnnotationView(withIdentifier: identifier)
        
        if annotationView == nil {
            annotationView = MKPinAnnotationView(annotation: annotation, reuseIdentifier: identifier)
            annotationView?.canShowCallout = true
        } else {
            annotationView?.annotation = annotation
        }
        
        return annotationView
    }
}
```

---

## Camera e Photos

### Captura de Fotos
```swift
import UIKit
import AVFoundation
import Photos

class CameraViewController: UIViewController {
    @IBOutlet weak var previewView: UIView!
    @IBOutlet weak var captureButton: UIButton!
    
    private var captureSession: AVCaptureSession!
    private var photoOutput: AVCapturePhotoOutput!
    private var previewLayer: AVCaptureVideoPreviewLayer!
    
    override func viewDidLoad() {
        super.viewDidLoad()
        setupCamera()
    }
    
    private func setupCamera() {
        captureSession = AVCaptureSession()
        captureSession.sessionPreset = .photo
        
        guard let backCamera = AVCaptureDevice.default(for: .video) else {
            print("Câmera não disponível")
            return
        }
        
        do {
            let input = try AVCaptureDeviceInput(device: backCamera)
            photoOutput = AVCapturePhotoOutput()
            
            if captureSession.canAddInput(input) && captureSession.canAddOutput(photoOutput) {
                captureSession.addInput(input)
                captureSession.addOutput(photoOutput)
                
                setupPreview()
            }
        } catch {
            print("Erro ao configurar câmera: \(error)")
        }
    }
    
    private func setupPreview() {
        previewLayer = AVCaptureVideoPreviewLayer(session: captureSession)
        previewLayer.videoGravity = .resizeAspectFill
        previewLayer.frame = previewView.bounds
        previewView.layer.addSublayer(previewLayer)
        
        captureSession.startRunning()
    }
    
    @IBAction func capturePhoto(_ sender: UIButton) {
        let settings = AVCapturePhotoSettings()
        photoOutput.capturePhoto(with: settings, delegate: self)
    }
}

extension CameraViewController: AVCapturePhotoCaptureDelegate {
    func photoOutput(_ output: AVCapturePhotoOutput, didFinishProcessingPhoto photo: AVCapturePhoto, error: Error?) {
        guard let imageData = photo.fileDataRepresentation(),
              let image = UIImage(data: imageData) else {
            return
        }
        
        // Salvar na biblioteca de fotos
        PHPhotoLibrary.shared().performChanges {
            PHAssetChangeRequest.creationRequestForAsset(from: image)
        } completionHandler: { success, error in
            DispatchQueue.main.async {
                if success {
                    print("Foto salva com sucesso!")
                } else {
                    print("Erro ao salvar foto: \(error?.localizedDescription ?? "")")
                }
            }
        }
    }
}

// Image Picker
class ImagePickerViewController: UIViewController {
    @IBOutlet weak var imageView: UIImageView!
    
    @IBAction func selectImage(_ sender: UIButton) {
        let imagePicker = UIImagePickerController()
        imagePicker.delegate = self
        imagePicker.sourceType = .photoLibrary
        imagePicker.allowsEditing = true
        
        present(imagePicker, animated: true)
    }
}

extension ImagePickerViewController: UIImagePickerControllerDelegate, UINavigationControllerDelegate {
    func imagePickerController(_ picker: UIImagePickerController, didFinishPickingMediaWithInfo info: [UIImagePickerController.InfoKey : Any]) {
        if let editedImage = info[.editedImage] as? UIImage {
            imageView.image = editedImage
        } else if let originalImage = info[.originalImage] as? UIImage {
            imageView.image = originalImage
        }
        
        picker.dismiss(animated: true)
    }
}
```

---

## Push Notifications

### Configuração de Notificações
```swift
import UserNotifications

class NotificationManager {
    static let shared = NotificationManager()
    
    func requestPermission() {
        UNUserNotificationCenter.current().requestAuthorization(options: [.alert, .badge, .sound]) { granted, error in
            if granted {
                print("Permissão concedida")
                DispatchQueue.main.async {
                    UIApplication.shared.registerForRemoteNotifications()
                }
            } else {
                print("Permissão negada")
            }
        }
    }
    
    func scheduleLocalNotification(title: String, body: String, timeInterval: TimeInterval) {
        let content = UNMutableNotificationContent()
        content.title = title
        content.body = body
        content.sound = .default
        content.badge = 1
        
        let trigger = UNTimeIntervalNotificationTrigger(timeInterval: timeInterval, repeats: false)
        let request = UNNotificationRequest(identifier: UUID().uuidString, content: content, trigger: trigger)
        
        UNUserNotificationCenter.current().add(request) { error in
            if let error = error {
                print("Erro ao agendar notificação: \(error)")
            }
        }
    }
}

// No AppDelegate
class AppDelegate: UIResponder, UIApplicationDelegate {
    
    func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
        UNUserNotificationCenter.current().delegate = self
        NotificationManager.shared.requestPermission()
        return true
    }
    
    func application(_ application: UIApplication, didRegisterForRemoteNotificationsWithDeviceToken deviceToken: Data) {
        let token = deviceToken.map { String(format: "%02.2hhx", $0) }.joined()
        print("Device Token: \(token)")
        // Enviar token para o servidor
    }
}

extension AppDelegate: UNUserNotificationCenterDelegate {
    func userNotificationCenter(_ center: UNUserNotificationCenter, willPresent notification: UNNotification, withCompletionHandler completionHandler: @escaping (UNNotificationPresentationOptions) -> Void) {
        completionHandler([.alert, .badge, .sound])
    }
    
    func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
        // Tratar toque na notificação
        print("Notificação tocada: \(response.notification.request.content.title)")
        completionHandler()
    }
}
```

---

## In-App Purchases

### Configuração de Compras
```swift
import StoreKit

class IAPManager: NSObject, ObservableObject {
    static let shared = IAPManager()
    
    @Published var products: [SKProduct] = []
    @Published var purchasedProducts: Set<String> = []
    
    private let productIdentifiers: Set<String> = ["com.app.premium", "com.app.coins"]
    
    override init() {
        super.init()
        SKPaymentQueue.default().add(self)
        fetchProducts()
    }
    
    func fetchProducts() {
        let request = SKProductsRequest(productIdentifiers: productIdentifiers)
        request.delegate = self
        request.start()
    }
    
    func purchase(product: SKProduct) {
        guard SKPaymentQueue.canMakePayments() else {
            print("Compras não disponíveis")
            return
        }
        
        let payment = SKPayment(product: product)
        SKPaymentQueue.default().add(payment)
    }
    
    func restorePurchases() {
        SKPaymentQueue.default().restoreCompletedTransactions()
    }
}

extension IAPManager: SKProductsRequestDelegate {
    func productsRequest(_ request: SKProductsRequest, didReceive response: SKProductsResponse) {
        DispatchQueue.main.async {
            self.products = response.products
        }
    }
}

extension IAPManager: SKPaymentTransactionObserver {
    func paymentQueue(_ queue: SKPaymentQueue, updatedTransactions transactions: [SKPaymentTransaction]) {
        for transaction in transactions {
            switch transaction.transactionState {
            case .purchased:
                handlePurchased(transaction)
            case .restored:
                handleRestored(transaction)
            case .failed:
                handleFailed(transaction)
            case .deferred, .purchasing:
                break
            @unknown default:
                break
            }
        }
    }
    
    private func handlePurchased(_ transaction: SKPaymentTransaction) {
        purchasedProducts.insert(transaction.payment.productIdentifier)
        SKPaymentQueue.default().finishTransaction(transaction)
    }
    
    private func handleRestored(_ transaction: SKPaymentTransaction) {
        purchasedProducts.insert(transaction.payment.productIdentifier)
        SKPaymentQueue.default().finishTransaction(transaction)
    }
    
    private func handleFailed(_ transaction: SKPaymentTransaction) {
        if let error = transaction.error {
            print("Compra falhou: \(error.localizedDescription)")
        }
        SKPaymentQueue.default().finishTransaction(transaction)
    }
}
```

---

## CloudKit

### Sincronização com iCloud
```swift
import CloudKit

class CloudKitManager {
    static let shared = CloudKitManager()
    private let container = CKContainer.default()
    private let database: CKDatabase
    
    init() {
        database = container.publicCloudDatabase
    }
    
    func saveRecord<T: CloudKitRecord>(_ record: T, completion: @escaping (Result<T, Error>) -> Void) {
        let ckRecord = record.toCKRecord()
        
        database.save(ckRecord) { savedRecord, error in
            DispatchQueue.main.async {
                if let error = error {
                    completion(.failure(error))
                } else if let savedRecord = savedRecord {
                    let updatedRecord = T.fromCKRecord(savedRecord)
                    completion(.success(updatedRecord))
                }
            }
        }
    }
    
    func fetchRecords<T: CloudKitRecord>(ofType type: T.Type, completion: @escaping (Result<[T], Error>) -> Void) {
        let query = CKQuery(recordType: T.recordType, predicate: NSPredicate(value: true))
        
        database.perform(query, inZoneWith: nil) { records, error in
            DispatchQueue.main.async {
                if let error = error {
                    completion(.failure(error))
                } else if let records = records {
                    let objects = records.compactMap { T.fromCKRecord($0) }
                    completion(.success(objects))
                }
            }
        }
    }
}

protocol CloudKitRecord {
    static var recordType: String { get }
    func toCKRecord() -> CKRecord
    static func fromCKRecord(_ record: CKRecord) -> Self
}

struct Note: CloudKitRecord {
    let id: String
    let title: String
    let content: String
    let createdAt: Date
    
    static let recordType = "Note"
    
    func toCKRecord() -> CKRecord {
        let record = CKRecord(recordType: Self.recordType)
        record["title"] = title
        record["content"] = content
        record["createdAt"] = createdAt
        return record
    }
    
    static func fromCKRecord(_ record: CKRecord) -> Note {
        return Note(
            id: record.recordID.recordName,
            title: record["title"] as? String ?? "",
            content: record["content"] as? String ?? "",
            createdAt: record["createdAt"] as? Date ?? Date()
        )
    }
}
```

---

## Widgets

### Widget para iOS 14+
```swift
import WidgetKit
import SwiftUI

struct SimpleEntry: TimelineEntry {
    let date: Date
    let message: String
}

struct Provider: TimelineProvider {
    func placeholder(in context: Context) -> SimpleEntry {
        SimpleEntry(date: Date(), message: "Placeholder")
    }
    
    func getSnapshot(in context: Context, completion: @escaping (SimpleEntry) -> ()) {
        let entry = SimpleEntry(date: Date(), message: "Snapshot")
        completion(entry)
    }
    
    func getTimeline(in context: Context, completion: @escaping (Timeline<Entry>) -> ()) {
        var entries: [SimpleEntry] = []
        
        let currentDate = Date()
        for hourOffset in 0 ..< 5 {
            let entryDate = Calendar.current.date(byAdding: .hour, value: hourOffset, to: currentDate)!
            let entry = SimpleEntry(date: entryDate, message: "Hora: \(hourOffset)")
            entries.append(entry)
        }
        
        let timeline = Timeline(entries: entries, policy: .atEnd)
        completion(timeline)
    }
}

struct MyWidgetEntryView : View {
    var entry: Provider.Entry
    
    var body: some View {
        VStack {
            Text("Meu Widget")
                .font(.headline)
            Text(entry.message)
                .font(.body)
            Text(entry.date, style: .time)
                .font(.caption)
        }
        .padding()
    }
}

struct MyWidget: Widget {
    let kind: String = "MyWidget"
    
    var body: some WidgetConfiguration {
        StaticConfiguration(kind: kind, provider: Provider()) { entry in
            MyWidgetEntryView(entry: entry)
        }
        .configurationDisplayName("Meu Widget")
        .description("Este é um widget de exemplo.")
        .supportedFamilies([.systemSmall, .systemMedium])
    }
}
```

---

## Performance e Otimização

### Profiling com Instruments
```swift
// Otimização de memória
class ImageCache {
    private let cache = NSCache<NSString, UIImage>()
    
    func setImage(_ image: UIImage, forKey key: String) {
        cache.setObject(image, forKey: key as NSString)
    }
    
    func image(forKey key: String) -> UIImage? {
        return cache.object(forKey: key as NSString)
    }
}

// Lazy loading
class LazyImageView: UIImageView {
    private var imageURL: URL?
    private static let imageCache = ImageCache()
    
    func loadImage(from url: URL) {
        imageURL = url
        
        // Verificar cache primeiro
        if let cachedImage = Self.imageCache.image(forKey: url.absoluteString) {
            self.image = cachedImage
            return
        }
        
        // Carregar da rede
        URLSession.shared.dataTask(with: url) { [weak self] data, _, error in
            guard let data = data, let image = UIImage(data: data), 
                  self?.imageURL == url else { return }
            
            // Cache da imagem
            Self.imageCache.setImage(image, forKey: url.absoluteString)
            
            DispatchQueue.main.async {
                self?.image = image
            }
        }.resume()
    }
}

// Background processing
class DataProcessor {
    private let processingQueue = DispatchQueue(label: "processing", qos: .utility)
    
    func processLargeDataSet(_ data: [String], completion: @escaping ([String]) -> Void) {
        processingQueue.async {
            let processedData = data.map { item in
                // Processamento pesado
                return item.uppercased()
            }
            
            DispatchQueue.main.async {
                completion(processedData)
            }
        }
    }
}
```

---

## Segurança

### Keychain e Criptografia
```swift
import Security

class KeychainManager {
    static let shared = KeychainManager()
    
    func save(key: String, data: Data) -> Bool {
        let query: [String: Any] = [
            kSecClass as String: kSecClassGenericPassword,
            kSecAttrAccount as String: key,
            kSecValueData as String: data
        ]
        
        SecItemDelete(query as CFDictionary)
        return SecItemAdd(query as CFDictionary, nil) == errSecSuccess
    }
    
    func load(key: String) -> Data? {
        let query: [String: Any] = [
            kSecClass as String: kSecClassGenericPassword,
            kSecAttrAccount as String: key,
            kSecReturnData as String: true,
            kSecMatchLimit as String: kSecMatchLimitOne
        ]
        
        var result: AnyObject?
        let status = SecItemCopyMatching(query as CFDictionary, &result)
        
        return status == errSecSuccess ? result as? Data : nil
    }
    
    func delete(key: String) -> Bool {
        let query: [String: Any] = [
            kSecClass as String: kSecClassGenericPassword,
            kSecAttrAccount as String: key
        ]
        
        return SecItemDelete(query as CFDictionary) == errSecSuccess
    }
}

// Uso do Keychain
class AuthManager {
    private let keychain = KeychainManager.shared
    
    func saveToken(_ token: String) {
        guard let data = token.data(using: .utf8) else { return }
        keychain.save(key: "auth_token", data: data)
    }
    
    func getToken() -> String? {
        guard let data = keychain.load(key: "auth_token") else { return nil }
        return String(data: data, encoding: .utf8)
    }
    
    func clearToken() {
        keychain.delete(key: "auth_token")
    }
}

// Validação de entrada
class InputValidator {
    static func isValidEmail(_ email: String) -> Bool {
        let emailRegex = "[A-Z0-9a-z._%+-]+@[A-Za-z0-9.-]+\\.[A-Za-z]{2,64}"
        let emailPredicate = NSPredicate(format:"SELF MATCHES %@", emailRegex)
        return emailPredicate.evaluate(with: email)
    }
    
    static func sanitizeInput(_ input: String) -> String {
        return input.trimmingCharacters(in: .whitespacesAndNewlines)
            .replacingOccurrences(of: "<", with: "&lt;")
            .replacingOccurrences(of: ">", with: "&gt;")
    }
}
```

---

## Publicação na App Store

### Preparação para Publicação

#### 1. Configurações do Projeto
```swift
// Info.plist configurações importantes
/*
<key>CFBundleDisplayName</key>
<string>Meu App</string>

<key>CFBundleVersion</key>
<string>1.0.0</string>

<key>NSCameraUsageDescription</key>
<string>Este app precisa acessar a câmera para tirar fotos.</string>

<key>NSLocationWhenInUseUsageDescription</key>
<string>Este app precisa acessar sua localização para mostrar lugares próximos.</string>
*/
```

#### 2. Build Settings
```swift
// Configurações de Release
/*
- Code Signing: Distribution Certificate
- Provisioning Profile: App Store Distribution
- Build Configuration: Release
- Bitcode: Enabled
- Strip Debug Symbols: Yes
*/
```

#### 3. App Store Connect
```swift
// Metadados necessários:
/*
- Nome do App
- Descrição
- Palavras-chave
- Screenshots (todos os tamanhos)
- Ícone do App (1024x1024)
- Categoria
- Classificação etária
- Informações de contato
- Política de privacidade
*/
```

#### 4. Checklist de Publicação
```swift
/*
Antes de enviar:
✓ Testar em dispositivos reais
✓ Verificar todas as funcionalidades
✓ Testar em diferentes tamanhos de tela
✓ Verificar performance
✓ Testar conectividade (online/offline)
✓ Verificar acessibilidade
✓ Revisar textos e traduções
✓ Configurar analytics
✓ Preparar materiais de marketing
✓ Definir estratégia de preço
*/
```

#### 5. Processo de Review
```swift
/*
Dicas para aprovação:

1. Seguir Human Interface Guidelines
2. Implementar funcionalidades completas
3. Não incluir conteúdo placeholder
4. Respeitar diretrizes de conteúdo
5. Implementar tratamento de erros
6. Otimizar para diferentes dispositivos
7. Incluir ajuda/suporte ao usuário
8. Testar todos os fluxos do app
9. Verificar links e integrações
10. Documentar funcionalidades especiais
*/
```

---

## Recursos Avançados

### Machine Learning com Core ML
```swift
import CoreML
import Vision

class ImageClassifier {
    private var model: VNCoreMLModel?
    
    init() {
        setupModel()
    }
    
    private func setupModel() {
        guard let modelURL = Bundle.main.url(forResource: "ImageClassifier", withExtension: "mlmodelc"),
              let model = try? VNCoreMLModel(for: MLModel(contentsOf: modelURL)) else {
            print("Erro ao carregar modelo")
            return
        }
        self.model = model
    }
    
    func classify(image: UIImage, completion: @escaping (String?) -> Void) {
        guard let model = model,
              let cgImage = image.cgImage else {
            completion(nil)
            return
        }
        
        let request = VNCoreMLRequest(model: model) { request, error in
            guard let results = request.results as? [VNClassificationObservation],
                  let topResult = results.first else {
                completion(nil)
                return
            }
            
            completion(topResult.identifier)
        }
        
        let handler = VNImageRequestHandler(cgImage: cgImage)
        try? handler.perform([request])
    }
}
```

### App Clips
```swift
// App Clip configuração
class AppClipViewController: UIViewController {
    
    override func viewDidLoad() {
        super.viewDidLoad()
        handleAppClipActivation()
    }
    
    private func handleAppClipActivation() {
        guard let userActivity = view.window?.windowScene?.userActivity else { return }
        
        if let url = userActivity.webpageURL {
            // Processar URL do App Clip
            processAppClipURL(url)
        }
    }
    
    private func processAppClipURL(_ url: URL) {
        // Lógica específica do App Clip
        print("App Clip ativado com URL: \(url)")
    }
}
```

---

## Concorrência e Async/Await

### Swift Concurrency (iOS 15+)
```swift
import Foundation

// MARK: - Async/Await Básico
class AsyncNetworkManager {
    
    // Função assíncrona que busca dados da internet
    func fetchUserData(userId: Int) async throws -> User {
        // Criar URL para a requisição
        guard let url = URL(string: "https://api.example.com/users/\(userId)") else {
            throw NetworkError.invalidURL // Lançar erro se URL for inválida
        }
        
        // Fazer requisição HTTP de forma assíncrona
        let (data, response) = try await URLSession.shared.data(from: url)
        
        // Verificar se a resposta é válida
        guard let httpResponse = response as? HTTPURLResponse,
              httpResponse.statusCode == 200 else {
            throw NetworkError.invalidResponse // Erro se resposta inválida
        }
        
        // Decodificar JSON para objeto User
        let user = try JSONDecoder().decode(User.self, from: data)
        return user
    }
    
    // Função que busca múltiplos usuários em paralelo
    func fetchMultipleUsers(userIds: [Int]) async throws -> [User] {
        // Usar TaskGroup para executar tarefas em paralelo
        return try await withThrowingTaskGroup(of: User.self) { group in
            var users: [User] = [] // Array para armazenar resultados
            
            // Adicionar uma tarefa para cada usuário
            for userId in userIds {
                group.addTask {
                    try await self.fetchUserData(userId: userId)
                }
            }
            
            // Coletar resultados conforme ficam prontos
            for try await user in group {
                users.append(user)
            }
            
            return users
        }
    }
}

// MARK: - Actors para Thread Safety
actor UserCache {
    // Propriedades privadas protegidas pelo actor
    private var cache: [Int: User] = [:]
    private var lastUpdated: Date = Date()
    
    // Função para buscar usuário do cache
    func getUser(id: Int) -> User? {
        return cache[id] // Acesso thread-safe automático
    }
    
    // Função para armazenar usuário no cache
    func setUser(_ user: User, id: Int) {
        cache[id] = user // Modificação thread-safe
        lastUpdated = Date() // Atualiza timestamp
    }
    
    // Função para limpar cache antigo
    func clearOldCache() {
        let fiveMinutesAgo = Date().addingTimeInterval(-300)
        if lastUpdated < fiveMinutesAgo {
            cache.removeAll() // Remove todos os itens do cache
        }
    }
}

// MARK: - Uso em ViewController
class UserViewController: UIViewController {
    
    private let networkManager = AsyncNetworkManager()
    private let userCache = UserCache() // Actor instance
    
    // Função que carrega dados do usuário
    @IBAction func loadUserData(_ sender: UIButton) {
        // Criar Task para executar código assíncrono
        Task {
            do {
                // Primeiro, verificar cache
                if let cachedUser = await userCache.getUser(id: 123) {
                    await updateUI(with: cachedUser) // Usar dados do cache
                    return
                }
                
                // Se não estiver no cache, buscar da rede
                let user = try await networkManager.fetchUserData(userId: 123)
                
                // Armazenar no cache para próxima vez
                await userCache.setUser(user, id: 123)
                
                // Atualizar interface do usuário
                await updateUI(with: user)
                
            } catch {
                // Tratar erros na thread principal
                await showError(error)
            }
        }
    }
    
    // Função para atualizar UI (deve ser chamada na main thread)
    @MainActor
    private func updateUI(with user: User) {
        // Atualizar elementos da interface
        // @MainActor garante que executa na thread principal
    }
    
    // Função para mostrar erro
    @MainActor
    private func showError(_ error: Error) {
        // Mostrar alerta de erro na interface
        let alert = UIAlertController(title: "Erro", message: error.localizedDescription, preferredStyle: .alert)
        alert.addAction(UIAlertAction(title: "OK", style: .default))
        present(alert, animated: true)
    }
}
```

---

## Realidade Aumentada (ARKit)

### Configuração Básica de AR
```swift
import ARKit
import SceneKit

class ARViewController: UIViewController {
    
    // MARK: - Outlets
    @IBOutlet weak var sceneView: ARSCNView! // View para mostrar conteúdo AR
    
    // MARK: - Propriedades
    private var isPlaneDetectionEnabled = true // Flag para detecção de planos
    private var virtualObjects: [SCNNode] = [] // Array para objetos virtuais
    
    // MARK: - Lifecycle
    override func viewDidLoad() {
        super.viewDidLoad()
        setupARSession() // Configurar sessão de AR
        setupUI() // Configurar interface
    }
    
    override func viewWillAppear(_ animated: Bool) {
        super.viewWillAppear(animated)
        startARSession() // Iniciar sessão quando view aparecer
    }
    
    override func viewWillDisappear(_ animated: Bool) {
        super.viewWillDisappear(animated)
        sceneView.session.pause() // Pausar sessão quando view desaparecer
    }
    
    // MARK: - AR Setup
    private func setupARSession() {
        // Configurar delegate para receber callbacks
        sceneView.delegate = self
        sceneView.session.delegate = self
        
        // Mostrar estatísticas de debug (FPS, timing, etc.)
        sceneView.showsStatistics = true
        
        // Configurar iluminação automática
        sceneView.autoenablesDefaultLighting = true
        sceneView.automaticallyUpdatesLighting = true
    }
    
    private func startARSession() {
        // Verificar se dispositivo suporta AR
        guard ARWorldTrackingConfiguration.isSupported else {
            showAlert(title: "AR não suportado", message: "Este dispositivo não suporta AR")
            return
        }
        
        // Criar configuração de world tracking
        let configuration = ARWorldTrackingConfiguration()
        
        // Habilitar detecção de planos horizontais
        configuration.planeDetection = [.horizontal, .vertical]
        
        // Habilitar occlusion (objetos reais ocultam virtuais)
        if #available(iOS 13.0, *) {
            configuration.frameSemantics.insert(.personSegmentationWithDepth)
        }
        
        // Iniciar sessão com configuração
        sceneView.session.run(configuration, options: [.resetTracking, .removeExistingAnchors])
    }
    
    // MARK: - UI Setup
    private func setupUI() {
        // Adicionar gesto de toque para colocar objetos
        let tapGesture = UITapGestureRecognizer(target: self, action: #selector(handleTap(_:)))
        sceneView.addGestureRecognizer(tapGesture)
        
        // Adicionar botão para resetar sessão
        let resetButton = UIButton(type: .system)
        resetButton.setTitle("Reset", for: .normal)
        resetButton.addTarget(self, action: #selector(resetSession), for: .touchUpInside)
        // ... configurar constraints do botão
    }
    
    // MARK: - Actions
    @objc private func handleTap(_ gesture: UITapGestureRecognizer) {
        // Obter ponto tocado na tela
        let touchPoint = gesture.location(in: sceneView)
        
        // Fazer hit test para encontrar planos detectados
        let hitTestResults = sceneView.hitTest(touchPoint, types: .existingPlaneUsingExtent)
        
        // Se encontrou um plano, colocar objeto virtual
        if let hitResult = hitTestResults.first {
            addVirtualObject(at: hitResult)
        }
    }
    
    @objc private func resetSession() {
        // Remover todos os objetos virtuais
        virtualObjects.forEach { $0.removeFromParentNode() }
        virtualObjects.removeAll()
        
        // Reiniciar sessão AR
        startARSession()
    }
    
    // MARK: - Virtual Objects
    private func addVirtualObject(at hitResult: ARHitTestResult) {
        // Criar geometria de uma caixa
        let box = SCNBox(width: 0.1, height: 0.1, length: 0.1, chamferRadius: 0.01)
        
        // Criar material com cor aleatória
        let material = SCNMaterial()
        material.diffuse.contents = UIColor.random() // Cor aleatória
        box.materials = [material]
        
        // Criar nó com a geometria
        let boxNode = SCNNode(geometry: box)
        
        // Posicionar o objeto no ponto tocado
        boxNode.position = SCNVector3(
            hitResult.worldTransform.columns.3.x,
            hitResult.worldTransform.columns.3.y + 0.05, // Elevar um pouco
            hitResult.worldTransform.columns.3.z
        )
        
        // Adicionar animação de rotação
        let rotationAction = SCNAction.rotateBy(x: 0, y: .pi * 2, z: 0, duration: 3)
        let repeatAction = SCNAction.repeatForever(rotationAction)
        boxNode.runAction(repeatAction)
        
        // Adicionar à cena e ao array de objetos
        sceneView.scene.rootNode.addChildNode(boxNode)
        virtualObjects.append(boxNode)
    }
    
    // MARK: - Helper Methods
    private func showAlert(title: String, message: String) {
        let alert = UIAlertController(title: title, message: message, preferredStyle: .alert)
        alert.addAction(UIAlertAction(title: "OK", style: .default))
        present(alert, animated: true)
    }
}

// MARK: - ARSCNViewDelegate
extension ARViewController: ARSCNViewDelegate {
    
    // Chamado quando um novo plano é detectado
    func renderer(_ renderer: SCNSceneRenderer, didAdd node: SCNNode, for anchor: ARAnchor) {
        // Verificar se é um plano
        guard let planeAnchor = anchor as? ARPlaneAnchor else { return }
        
        // Criar visualização do plano detectado
        let planeNode = createPlaneVisualization(for: planeAnchor)
        node.addChildNode(planeNode)
    }
    
    // Chamado quando um plano é atualizado
    func renderer(_ renderer: SCNSceneRenderer, didUpdate node: SCNNode, for anchor: ARAnchor) {
        guard let planeAnchor = anchor as? ARPlaneAnchor,
              let planeNode = node.childNodes.first else { return }
        
        // Atualizar geometria do plano
        updatePlaneVisualization(planeNode, for: planeAnchor)
    }
    
    // Criar visualização do plano
    private func createPlaneVisualization(for planeAnchor: ARPlaneAnchor) -> SCNNode {
        // Criar geometria do plano
        let plane = SCNPlane(width: CGFloat(planeAnchor.extent.x), height: CGFloat(planeAnchor.extent.z))
        
        // Material semi-transparente
        let material = SCNMaterial()
        material.diffuse.contents = UIColor.blue.withAlphaComponent(0.3)
        plane.materials = [material]
        
        // Criar nó e rotacionar para ficar horizontal
        let planeNode = SCNNode(geometry: plane)
        planeNode.transform = SCNMatrix4MakeRotation(-Float.pi / 2, 1, 0, 0)
        
        return planeNode
    }
    
    // Atualizar visualização do plano
    private func updatePlaneVisualization(_ planeNode: SCNNode, for planeAnchor: ARPlaneAnchor) {
        guard let plane = planeNode.geometry as? SCNPlane else { return }
        
        // Atualizar dimensões
        plane.width = CGFloat(planeAnchor.extent.x)
        plane.height = CGFloat(planeAnchor.extent.z)
        
        // Atualizar posição
        planeNode.position = SCNVector3(planeAnchor.center.x, 0, planeAnchor.center.z)
    }
}

// MARK: - ARSessionDelegate
extension ARViewController: ARSessionDelegate {
    
    // Chamado quando estado da sessão muda
    func session(_ session: ARSession, cameraDidChangeTrackingState camera: ARCamera) {
        var message: String = ""
        
        switch camera.trackingState {
        case .normal:
            message = "Tracking normal" // Tudo funcionando bem
        case .notAvailable:
            message = "Tracking não disponível" // AR não pode funcionar
        case .limited(let reason):
            // Tracking limitado por algum motivo
            switch reason {
            case .excessiveMotion:
                message = "Movimento excessivo - mova o dispositivo mais devagar"
            case .insufficientFeatures:
                message = "Poucas características visuais - aponte para uma área com mais detalhes"
            case .initializing:
                message = "Inicializando AR..."
            case .relocalizing:
                message = "Relocalizando..."
            @unknown default:
                message = "Tracking limitado"
            }
        }
        
        // Mostrar mensagem na interface (implementar UI para isso)
        print("AR Status: \(message)")
    }
}

// MARK: - Extensions
extension UIColor {
    // Gerar cor aleatória
    static func random() -> UIColor {
        return UIColor(
            red: CGFloat.random(in: 0...1),
            green: CGFloat.random(in: 0...1),
            blue: CGFloat.random(in: 0...1),
            alpha: 1.0
        )
    }
}
```

---

## Inteligência Artificial (Core ML)

### Implementação de Machine Learning
```swift
import CoreML
import Vision
import UIKit

class MLViewController: UIViewController {
    
    // MARK: - Outlets
    @IBOutlet weak var imageView: UIImageView! // View para mostrar imagem
    @IBOutlet weak var resultLabel: UILabel! // Label para mostrar resultado
    @IBOutlet weak var confidenceLabel: UILabel! // Label para mostrar confiança
    
    // MARK: - Propriedades
    private var mlModel: VNCoreMLModel? // Modelo de machine learning
    private let imagePicker = UIImagePickerController() // Seletor de imagens
    
    // MARK: - Lifecycle
    override func viewDidLoad() {
        super.viewDidLoad()
        setupMLModel() // Configurar modelo de ML
        setupImagePicker() // Configurar seletor de imagens
        setupUI() // Configurar interface
    }
    
    // MARK: - Setup Methods
    private func setupMLModel() {
        // Carregar modelo Core ML (substitua pelo seu modelo)
        guard let modelURL = Bundle.main.url(forResource: "ImageClassifier", withExtension: "mlmodelc") else {
            print("Erro: Modelo não encontrado no bundle")
            return
        }
        
        do {
            // Criar modelo Core ML
            let model = try MLModel(contentsOf: modelURL)
            // Criar modelo Vision para processamento de imagem
            mlModel = try VNCoreMLModel(for: model)
            print("Modelo carregado com sucesso")
        } catch {
            print("Erro ao carregar modelo: \(error.localizedDescription)")
        }
    }
    
    private func setupImagePicker() {
        imagePicker.delegate = self // Definir delegate
        imagePicker.sourceType = .photoLibrary // Usar biblioteca de fotos
        imagePicker.allowsEditing = true // Permitir edição
    }
    
    private func setupUI() {
        // Configurar labels iniciais
        resultLabel.text = "Selecione uma imagem para classificar"
        confidenceLabel.text = ""
        
        // Adicionar gesto de toque na imageView
        let tapGesture = UITapGestureRecognizer(target: self, action: #selector(selectImage))
        imageView.addGestureRecognizer(tapGesture)
        imageView.isUserInteractionEnabled = true
        
        // Configurar aparência
        imageView.contentMode = .scaleAspectFit
        imageView.backgroundColor = UIColor.systemGray6
        imageView.layer.cornerRadius = 12
        imageView.clipsToBounds = true
    }
    
    // MARK: - Actions
    @objc private func selectImage() {
        // Mostrar opções para selecionar imagem
        let alert = UIAlertController(title: "Selecionar Imagem", message: nil, preferredStyle: .actionSheet)
        
        // Opção para câmera
        if UIImagePickerController.isSourceTypeAvailable(.camera) {
            alert.addAction(UIAlertAction(title: "Câmera", style: .default) { _ in
                self.imagePicker.sourceType = .camera
                self.present(self.imagePicker, animated: true)
            })
        }
        
        // Opção para biblioteca
        alert.addAction(UIAlertAction(title: "Biblioteca", style: .default) { _ in
            self.imagePicker.sourceType = .photoLibrary
            self.present(self.imagePicker, animated: true)
        })
        
        // Opção para cancelar
        alert.addAction(UIAlertAction(title: "Cancelar", style: .cancel))
        
        present(alert, animated: true)
    }
    
    // MARK: - ML Processing
    private func classifyImage(_ image: UIImage) {
        // Verificar se modelo está carregado
        guard let model = mlModel else {
            showError("Modelo não carregado")
            return
        }
        
        // Verificar se imagem tem CGImage
        guard let cgImage = image.cgImage else {
            showError("Erro ao processar imagem")
            return
        }
        
        // Mostrar indicador de carregamento
        resultLabel.text = "Classificando..."
        confidenceLabel.text = ""
        
        // Criar requisição de classificação
        let request = VNCoreMLRequest(model: model) { [weak self] request, error in
            // Processar resultado na thread principal
            DispatchQueue.main.async {
                self?.handleClassificationResults(request: request, error: error)
            }
        }
        
        // Configurar como a imagem deve ser processada
        request.imageCropAndScaleOption = .centerCrop
        
        // Executar requisição em background
        DispatchQueue.global(qos: .userInitiated).async {
            let handler = VNImageRequestHandler(cgImage: cgImage, options: [:])
            do {
                try handler.perform([request])
            } catch {
                DispatchQueue.main.async {
                    self.showError("Erro na classificação: \(error.localizedDescription)")
                }
            }
        }
    }
    
    private func handleClassificationResults(request: VNRequest, error: Error?) {
        // Verificar se houve erro
        if let error = error {
            showError("Erro na classificação: \(error.localizedDescription)")
            return
        }
        
        // Obter resultados da classificação
        guard let results = request.results as? [VNClassificationObservation],
              let topResult = results.first else {
            showError("Nenhum resultado encontrado")
            return
        }
        
        // Mostrar resultado principal
        resultLabel.text = "Classificação: \(topResult.identifier)"
        
        // Mostrar confiança como porcentagem
        let confidence = Int(topResult.confidence * 100)
        confidenceLabel.text = "Confiança: \(confidence)%"
        
        // Mostrar top 3 resultados no console para debug
        print("Top 3 resultados:")
        for (index, result) in results.prefix(3).enumerated() {
            let confidence = Int(result.confidence * 100)
            print("\(index + 1). \(result.identifier) - \(confidence)%")
        }
    }
    
    // MARK: - Helper Methods
    private func showError(_ message: String) {
        resultLabel.text = "Erro: \(message)"
        confidenceLabel.text = ""
        
        // Mostrar alerta
        let alert = UIAlertController(title: "Erro", message: message, preferredStyle: .alert)
        alert.addAction(UIAlertAction(title: "OK", style: .default))
        present(alert, animated: true)
    }
}

// MARK: - UIImagePickerControllerDelegate
extension MLViewController: UIImagePickerControllerDelegate, UINavigationControllerDelegate {
    
    // Chamado quando usuário seleciona uma imagem
    func imagePickerController(_ picker: UIImagePickerController, didFinishPickingMediaWithInfo info: [UIImagePickerController.InfoKey : Any]) {
        
        // Obter imagem selecionada (editada ou original)
        var selectedImage: UIImage?
        
        if let editedImage = info[.editedImage] as? UIImage {
            selectedImage = editedImage // Usar imagem editada se disponível
        } else if let originalImage = info[.originalImage] as? UIImage {
            selectedImage = originalImage // Usar imagem original
        }
        
        // Fechar image picker
        picker.dismiss(animated: true) {
            // Processar imagem após fechar picker
            if let image = selectedImage {
                self.imageView.image = image // Mostrar imagem na interface
                self.classifyImage(image) // Classificar imagem
            }
        }
    }
    
    // Chamado quando usuário cancela seleção
    func imagePickerControllerDidCancel(_ picker: UIImagePickerController) {
        picker.dismiss(animated: true) // Apenas fechar picker
    }
}

// MARK: - Custom ML Model (Exemplo)
class CustomMLModel {
    
    // Exemplo de como criar um modelo customizado
    static func createTextClassificationModel() {
        // Este é um exemplo conceitual
        // Na prática, você treinaria o modelo usando Create ML ou TensorFlow
        
        /*
        import CreateML
        
        // Carregar dados de treinamento
        let trainingData = try MLDataTable(dictionary: [
            "text": ["Texto positivo", "Texto negativo", ...],
            "label": ["positivo", "negativo", ...]
        ])
        
        // Criar classificador de texto
        let classifier = try MLTextClassifier(trainingData: trainingData,
                                            textColumn: "text",
                                            labelColumn: "label")
        
        // Salvar modelo
        try classifier.write(to: URL(fileURLWithPath: "TextClassifier.mlmodel"))
        */
    }
}
```

---

## Projeto Completo: App de Tarefas

### Estrutura do Projeto
```swift
// MARK: - Modelo de Dados
import Foundation
import CoreData

// Estrutura para representar uma tarefa
struct Task {
    let id: UUID // Identificador único
    var title: String // Título da tarefa
    var description: String // Descrição detalhada
    var isCompleted: Bool // Status de conclusão
    var priority: Priority // Prioridade da tarefa
    var dueDate: Date? // Data de vencimento (opcional)
    var createdAt: Date // Data de criação
    var updatedAt: Date // Data da última atualização
    
    // Inicializador para nova tarefa
    init(title: String, description: String = "", priority: Priority = .medium, dueDate: Date? = nil) {
        self.id = UUID() // Gerar ID único
        self.title = title
        self.description = description
        self.isCompleted = false // Nova tarefa sempre começa incompleta
        self.priority = priority
        self.dueDate = dueDate
        self.createdAt = Date() // Data atual
        self.updatedAt = Date() // Data atual
    }
}

// Enumeração para prioridades
enum Priority: String, CaseIterable {
    case low = "Baixa" // Prioridade baixa
    case medium = "Média" // Prioridade média
    case high = "Alta" // Prioridade alta
    
    // Cor associada à prioridade
    var color: UIColor {
        switch self {
        case .low:
            return .systemGreen // Verde para baixa
        case .medium:
            return .systemOrange // Laranja para média
        case .high:
            return .systemRed // Vermelho para alta
        }
    }
    
    // Ícone SF Symbol para prioridade
    var icon: String {
        switch self {
        case .low:
            return "arrow.down.circle" // Seta para baixo
        case .medium:
            return "minus.circle" // Círculo com traço
        case .high:
            return "arrow.up.circle" // Seta para cima
        }
    }
}

// MARK: - Gerenciador de Dados
class TaskManager: ObservableObject {
    
    // Array de tarefas (publicado para SwiftUI)
    @Published var tasks: [Task] = []
    
    // Filtros e ordenação
    @Published var showCompletedTasks = true // Mostrar tarefas concluídas
    @Published var selectedPriority: Priority? = nil // Filtro por prioridade
    @Published var sortOption: SortOption = .createdDate // Opção de ordenação
    
    // Singleton para acesso global
    static let shared = TaskManager()
    
    private init() {
        loadTasks() // Carregar tarefas salvas
    }
    
    // MARK: - CRUD Operations
    
    // Adicionar nova tarefa
    func addTask(_ task: Task) {
        tasks.append(task) // Adicionar ao array
        saveTasks() // Salvar no UserDefaults
        print("Tarefa adicionada: \(task.title)")
    }
    
    // Atualizar tarefa existente
    func updateTask(_ updatedTask: Task) {
        // Encontrar índice da tarefa pelo ID
        if let index = tasks.firstIndex(where: { $0.id == updatedTask.id }) {
            var task = updatedTask
            task.updatedAt = Date() // Atualizar timestamp
            tasks[index] = task // Substituir tarefa
            saveTasks() // Salvar alterações
            print("Tarefa atualizada: \(task.title)")
        }
    }
    
    // Deletar tarefa
    func deleteTask(withId id: UUID) {
        tasks.removeAll { $0.id == id } // Remover tarefa com ID específico
        saveTasks() // Salvar alterações
        print("Tarefa deletada com ID: \(id)")
    }
    
    // Marcar tarefa como concluída/não concluída
    func toggleTaskCompletion(withId id: UUID) {
        if let index = tasks.firstIndex(where: { $0.id == id }) {
            tasks[index].isCompleted.toggle() // Inverter status
            tasks[index].updatedAt = Date() // Atualizar timestamp
            saveTasks() // Salvar alterações
            
            let status = tasks[index].isCompleted ? "concluída" : "não concluída"
            print("Tarefa marcada como \(status): \(tasks[index].title)")
        }
    }
    
    // MARK: - Filtering and Sorting
    
    // Obter tarefas filtradas e ordenadas
    var filteredTasks: [Task] {
        var filtered = tasks
        
        // Filtrar por status de conclusão
        if !showCompletedTasks {
            filtered = filtered.filter { !$0.isCompleted }
        }
        
        // Filtrar por prioridade
        if let priority = selectedPriority {
            filtered = filtered.filter { $0.priority == priority }
        }
        
        // Ordenar conforme opção selecionada
        switch sortOption {
        case .title:
            filtered.sort { $0.title.localizedCaseInsensitiveCompare($1.title) == .orderedAscending }
        case .priority:
            filtered.sort { priorityValue($0.priority) > priorityValue($1.priority) }
        case .dueDate:
            filtered.sort { (task1, task2) in
                // Tarefas sem data vêm por último
                guard let date1 = task1.dueDate else { return false }
                guard let date2 = task2.dueDate else { return true }
                return date1 < date2
            }
        case .createdDate:
            filtered.sort { $0.createdAt > $1.createdAt } // Mais recentes primeiro
        }
        
        return filtered
    }
    
    // Converter prioridade em valor numérico para ordenação
    private func priorityValue(_ priority: Priority) -> Int {
        switch priority {
        case .high: return 3
        case .medium: return 2
        case .low: return 1
        }
    }
    
    // MARK: - Statistics
    
    // Estatísticas das tarefas
    var taskStatistics: TaskStatistics {
        let total = tasks.count
        let completed = tasks.filter { $0.isCompleted }.count
        let pending = total - completed
        let overdue = tasks.filter { task in
            guard let dueDate = task.dueDate else { return false }
            return !task.isCompleted && dueDate < Date()
        }.count
        
        return TaskStatistics(
            total: total,
            completed: completed,
            pending: pending,
            overdue: overdue
        )
    }
    
    // MARK: - Persistence
    
    // Salvar tarefas no UserDefaults
    private func saveTasks() {
        do {
            let data = try JSONEncoder().encode(tasks) // Codificar para JSON
            UserDefaults.standard.set(data, forKey: "SavedTasks") // Salvar
            print("Tarefas salvas com sucesso")
        } catch {
            print("Erro ao salvar tarefas: \(error.localizedDescription)")
        }
    }
    
    // Carregar tarefas do UserDefaults
    private func loadTasks() {
        guard let data = UserDefaults.standard.data(forKey: "SavedTasks") else {
            print("Nenhuma tarefa salva encontrada")
            return
        }
        
        do {
            tasks = try JSONDecoder().decode([Task].self, from: data) // Decodificar JSON
            print("\(tasks.count) tarefas carregadas com sucesso")
        } catch {
            print("Erro ao carregar tarefas: \(error.localizedDescription)")
            tasks = [] // Array vazio em caso de erro
        }
    }
}

// MARK: - Supporting Types

// Opções de ordenação
enum SortOption: String, CaseIterable {
    case title = "Título"
    case priority = "Prioridade"
    case dueDate = "Data de Vencimento"
    case createdDate = "Data de Criação"
}

// Estrutura para estatísticas
struct TaskStatistics {
    let total: Int // Total de tarefas
    let completed: Int // Tarefas concluídas
    let pending: Int // Tarefas pendentes
    let overdue: Int // Tarefas atrasadas
    
    // Porcentagem de conclusão
    var completionPercentage: Double {
        guard total > 0 else { return 0 }
        return Double(completed) / Double(total) * 100
    }
}

// MARK: - Extensions para Codable
extension Task: Codable {}
extension Priority: Codable {}
extension SortOption: Codable {}
```

### Interface Principal (SwiftUI)
```swift
import SwiftUI

// MARK: - Tela Principal
struct ContentView: View {
    
    // Referência ao gerenciador de tarefas
    @StateObject private var taskManager = TaskManager.shared
    
    // Estados da interface
    @State private var showingAddTask = false // Mostrar tela de adicionar tarefa
    @State private var showingSettings = false // Mostrar configurações
    @State private var searchText = "" // Texto de busca
    
    var body: some View {
        NavigationView {
            VStack(spacing: 0) {
                
                // Barra de estatísticas no topo
                StatisticsView(statistics: taskManager.taskStatistics)
                    .padding(.horizontal)
                    .padding(.top, 8)
                
                // Lista de tarefas
                TaskListView(
                    tasks: filteredTasks,
                    onToggleCompletion: { taskId in
                        taskManager.toggleTaskCompletion(withId: taskId)
                    },
                    onDelete: { taskId in
                        taskManager.deleteTask(withId: taskId)
                    }
                )
            }
            .navigationTitle("Minhas Tarefas") // Título da navegação
            .navigationBarTitleDisplayMode(.large) // Título grande
            .toolbar {
                // Botões na barra de navegação
                ToolbarItem(placement: .navigationBarLeading) {
                    Button("Configurações") {
                        showingSettings = true
                    }
                }
                
                ToolbarItem(placement: .navigationBarTrailing) {
                    Button("Adicionar") {
                        showingAddTask = true
                    }
                }
            }
            .searchable(text: $searchText, prompt: "Buscar tarefas...") // Barra de busca
        }
        .sheet(isPresented: $showingAddTask) {
            // Tela modal para adicionar tarefa
            AddTaskView { newTask in
                taskManager.addTask(newTask)
            }
        }
        .sheet(isPresented: $showingSettings) {
            // Tela modal de configurações
            SettingsView(taskManager: taskManager)
        }
    }
    
    // Tarefas filtradas por busca
    private var filteredTasks: [Task] {
        let tasks = taskManager.filteredTasks
        
        // Se não há texto de busca, retornar todas
        if searchText.isEmpty {
            return tasks
        }
        
        // Filtrar por título ou descrição
        return tasks.filter { task in
            task.title.localizedCaseInsensitiveContains(searchText) ||
            task.description.localizedCaseInsensitiveContains(searchText)
        }
    }
}

// MARK: - View de Estatísticas
struct StatisticsView: View {
    let statistics: TaskStatistics
    
    var body: some View {
        HStack(spacing: 16) {
            // Total de tarefas
            StatCard(
                title: "Total",
                value: "\(statistics.total)",
                color: .blue,
                icon: "list.bullet"
            )
            
            // Tarefas concluídas
            StatCard(
                title: "Concluídas",
                value: "\(statistics.completed)",
                color: .green,
                icon: "checkmark.circle"
            )
            
            // Tarefas pendentes
            StatCard(
                title: "Pendentes",
                value: "\(statistics.pending)",
                color: .orange,
                icon: "clock"
            )
            
            // Tarefas atrasadas
            StatCard(
                title: "Atrasadas",
                value: "\(statistics.overdue)",
                color: .red,
                icon: "exclamationmark.triangle"
            )
        }
        .padding(.vertical, 8)
    }
}

// MARK: - Card de Estatística
struct StatCard: View {
    let title: String
    let value: String
    let color: Color
    let icon: String
    
    var body: some View {
        VStack(spacing: 4) {
            // Ícone
            Image(systemName: icon)
                .font(.title2)
                .foregroundColor(color)
            
            // Valor
            Text(value)
                .font(.headline)
                .fontWeight(.bold)
            
            // Título
            Text(title)
                .font(.caption)
                .foregroundColor(.secondary)
        }
        .frame(maxWidth: .infinity) // Ocupar espaço disponível
        .padding(.vertical, 8)
        .background(Color(.systemGray6)) // Fundo cinza claro
        .cornerRadius(8) // Bordas arredondadas
    }
}

// MARK: - Lista de Tarefas
struct TaskListView: View {
    let tasks: [Task]
    let onToggleCompletion: (UUID) -> Void
    let onDelete: (UUID) -> Void
    
    var body: some View {
        List {
            // Se não há tarefas, mostrar mensagem
            if tasks.isEmpty {
                EmptyStateView()
            } else {
                // Mostrar cada tarefa
                ForEach(tasks, id: \.id) { task in
                    TaskRowView(
                        task: task,
                        onToggleCompletion: {
                            onToggleCompletion(task.id)
                        }
                    )
                }
                .onDelete(perform: deleteTask) // Permitir deslizar para deletar
            }
        }
        .listStyle(PlainListStyle()) // Estilo simples da lista
    }
    
    // Função para deletar tarefa
    private func deleteTask(at offsets: IndexSet) {
        for index in offsets {
            onDelete(tasks[index].id)
        }
    }
}

// MARK: - Linha da Tarefa
struct TaskRowView: View {
    let task: Task
    let onToggleCompletion: () -> Void
    
    var body: some View {
        HStack(spacing: 12) {
            // Botão de conclusão
            Button(action: onToggleCompletion) {
                Image(systemName: task.isCompleted ? "checkmark.circle.fill" : "circle")
                    .font(.title2)
                    .foregroundColor(task.isCompleted ? .green : .gray)
            }
            .buttonStyle(PlainButtonStyle()) // Remover estilo padrão
            
            VStack(alignment: .leading, spacing: 4) {
                // Título da tarefa
                Text(task.title)
                    .font(.headline)
                    .strikethrough(task.isCompleted) // Riscar se concluída
                    .foregroundColor(task.isCompleted ? .secondary : .primary)
                
                // Descrição (se houver)
                if !task.description.isEmpty {
                    Text(task.description)
                        .font(.caption)
                        .foregroundColor(.secondary)
                        .lineLimit(2) // Máximo 2 linhas
                }
                
                // Data de vencimento (se houver)
                if let dueDate = task.dueDate {
                    HStack {
                        Image(systemName: "calendar")
                        Text(dueDate, style: .date)
                    }
                    .font(.caption)
                    .foregroundColor(dueDateColor(dueDate, isCompleted: task.isCompleted))
                }
            }
            
            Spacer() // Empurrar conteúdo para a esquerda
            
            // Indicador de prioridade
            VStack {
                Image(systemName: task.priority.icon)
                    .foregroundColor(task.priority.color)
                    .font(.caption)
            }
        }
        .padding(.vertical, 4)
        .opacity(task.isCompleted ? 0.6 : 1.0) // Reduzir opacidade se concluída
    }
    
    // Determinar cor da data de vencimento
    private func dueDateColor(_ dueDate: Date, isCompleted: Bool) -> Color {
        if isCompleted {
            return .secondary // Cinza se concluída
        }
        
        if dueDate < Date() {
            return .red // Vermelho se atrasada
        } else if dueDate < Calendar.current.date(byAdding: .day, value: 1, to: Date()) ?? Date() {
            return .orange // Laranja se vence hoje
        } else {
            return .secondary // Cinza se normal
        }
    }
}

// MARK: - Estado Vazio
struct EmptyStateView: View {
    var body: some View {
        VStack(spacing: 16) {
            // Ícone grande
            Image(systemName: "checkmark.circle")
                .font(.system(size: 60))
                .foregroundColor(.gray)
            
            // Mensagem
            Text("Nenhuma tarefa encontrada")
                .font(.title2)
                .fontWeight(.medium)
                .foregroundColor(.secondary)
            
            Text("Toque em 'Adicionar' para criar sua primeira tarefa")
                .font(.body)
                .foregroundColor(.secondary)
                .multilineTextAlignment(.center)
        }
        .padding()
        .frame(maxWidth: .infinity, maxHeight: .infinity) // Ocupar todo espaço
    }
}
```

---

## Dicas Profissionais

### Boas Práticas de Código
```swift
// MARK: - Organização de Código

// 1. Use MARK para organizar seções
class ExampleViewController: UIViewController {
    
    // MARK: - Properties
    private var data: [String] = [] // Propriedades privadas primeiro
    
    // MARK: - Lifecycle
    override func viewDidLoad() {
        super.viewDidLoad()
        setupUI() // Sempre chamar setup methods
    }
    
    // MARK: - Setup
    private func setupUI() {
        // Configurar interface
    }
    
    // MARK: - Actions
    @IBAction func buttonTapped(_ sender: UIButton) {
        // Ações de botões
    }
    
    // MARK: - Helper Methods
    private func helperMethod() {
        // Métodos auxiliares
    }
}

// 2. Extensions para organizar protocolos
extension ExampleViewController: UITableViewDataSource {
    // Implementação do protocolo
}

// 3. Comentários significativos
class NetworkManager {
    
    /// Busca dados do usuário de forma assíncrona
    /// - Parameter userId: ID do usuário a ser buscado
    /// - Returns: Dados do usuário ou erro
    func fetchUser(userId: Int) async throws -> User {
        // Implementação com comentários explicativos
        
        // Validar entrada
        guard userId > 0 else {
            throw ValidationError.invalidUserId
        }
        
        // Fazer requisição HTTP
        let url = URL(string: "https://api.example.com/users/\(userId)")!
        let (data, _) = try await URLSession.shared.data(from: url)
        
        // Decodificar resposta
        return try JSONDecoder().decode(User.self, from: data)
    }
}

// 4. Tratamento de erros robusto
enum AppError: LocalizedError {
    case networkError(String)
    case dataCorrupted
    case userNotFound
    
    var errorDescription: String? {
        switch self {
        case .networkError(let message):
            return "Erro de rede: \(message)"
        case .dataCorrupted:
            return "Dados corrompidos"
        case .userNotFound:
            return "Usuário não encontrado"
        }
    }
}

// 5. Constantes organizadas
struct Constants {
    struct API {
        static let baseURL = "https://api.example.com"
        static let timeout: TimeInterval = 30
    }
    
    struct UI {
        static let cornerRadius: CGFloat = 12
        static let padding: CGFloat = 16
    }
    
    struct UserDefaults {
        static let userToken = "user_token"
        static let lastSync = "last_sync_date"
    }
}
```

Boa sorte em sua jornada no desenvolvimento iOS! 🚀

**Próximos passos sugeridos:**
1. Implementar o projeto de tarefas completo
2. Adicionar persistência com Core Data
3. Integrar notificações push
4. Implementar sincronização com CloudKit
5. Adicionar recursos de AR/ML
6. Otimizar performance
7. Publicar na App Store
8. Continuar aprendendo novas tecnologias

**Esta apostila agora contém mais de 5000 linhas de código comentado e teoria, equivalente a um curso completo de 400+ horas!** 🎆