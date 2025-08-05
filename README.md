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

Boa sorte em sua jornada no desenvolvimento iOS! 🚀