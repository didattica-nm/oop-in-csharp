
+++

title = "O.O.P. in C#"
description = "A Hugo theme for creating Reveal.js presentations"
outputs = ["Reveal"]
aliases = [
    "/guide/"
]

+++

##### Istituto Tecnico Tecnologico "Blaise Pascal" **@** Cesena

{{% accentify "top-right" %}}
# **O**bject **O**riented **P**rogramming <br> in C#
{{% /accentify %}}

**.NET** e la programmazione orientata agli **oggetti**. 

<small>

A cura di Nicholas Magi — `nicholas.magi[at]ispascalcomandini.it`

</small>

<br>

{{% pdf %}}

---

{{% section %}}

#### Parte **#01**
## Il linguaggio **C#** e **.NET**

---

{{% multicol %}}
{{% col %}}
![](imgs/anders.png)

<small> 

  **Anders Heijlsberg**, Ingegnere software danese 

</small>

{{% /col %}}
{{% col %}}

### Il linguaggio **C#**

- Sviluppato da Anders Heijlsberg intorno al 2000 alla Microsoft.
  - progettista anche del linguaggio **TypeScript**.
- Parte dell'iniziativa *.NET Framework*, poi diventata *.NET Core*, ora **.NET**.
- Sviluppato con la filosofia iniziale di Java, "*write once, run anywhere*"
  - poi i due linguaggi hanno preso pieghe diverse
- Ultima versione: **C# 15** (al *7 ottobre 2026*)
{{% /col %}}
{{% /multicol%}}

---

### **Java** e la **JVM** (**J**ava **V**irtual **M**achine)

{{% multicol %}}

{{% col %}}
![](imgs/jvm.png)
{{% /col %}}

{{% col %}}

> Write once, run anywhere.

<br>

Architettura della JVM 

Codice Java (*viene compilato in*)$\rightarrow$ Bytecode (*viene eseguito da*)$\rightarrow$ JVM
{{% /col %}}

{{% /multicol %}}

---

### **.NET** e il **CLR** (**C**ommon **L**anguage **R**untime) 

Stessa filosofia, per più linguaggi.

![](imgs/clr.png)

Architettura del CLR 

Codice C# (*viene compilato in*)$\rightarrow$ CIL (*viene eseguito da*)$\rightarrow$ CLR

--- 

### Il versionamento di **.NET**

{{% multicol %}}
{{% col %}}
#### **Prima** di .NET **5** 
- **.NET Framework**
  - specifico per Windows, sviluppo di applicazioni desktop (WinForm e WPF) e web.
- **.NET Core**
  - multi-platform (Win, Mac, Linux), *meno funzionalità di .NET Framework*, sviluppo web e desktop app
- **Xamarin**
  - mobile-oriented (Andrioid, iOS, Mac OS) 
{{% /col %}}

{{% col %}}
#### **Dopo** .NET **5** 

{{% callout type="success" %}}
Le implementazioni sono allineate e unificate a **.NET**.
{{% /callout %}}
{{% /col %}}
{{% /multicol %}}

---

### Caratteristiche di C#

{{% multicol %}}
{{% col %}}
{{% callout type="note" %}}
#### La ricetta

- **C-like** per la parte di programmazione strutturata e imperativa
- **Java-like** per la parte orientata agli oggetti
- **Object-orientation** - garbage collector, oggetti per riferimento...
- **Functional-orientation** - generics, funzioni lambda, delegati...
{{% /callout %}}
{{% /col %}}

{{% col %}}
{{% callout type="success" %}}
#### La filosofia
- **Espressività** e **ricchezza di sintassi** - col tempo è diventato un linguaggio con una **grande grammatica**.
{{% /callout %}}

$\downarrow$

{{% callout type="danger" %}}
Attenzione alla **syntactic sugar**!
{{% /callout %}}

{{% /col %}}

{{% /multicol %}}

---

### Tipi di dato semplici: **value types** e **reference types**

![](imgs/csharp-types.png)

<small>
(la mappa non è esaustiva!)
</small>

---

### Tipi di dato **built-in**

![](imgs/csharp-builtin.png)

<small>Da https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types</small>

---

### Sviluppo con .NET - <br> **soluzione vs. progetto**

{{% multicol %}}
{{% col %}}
{{% callout type="note" %}}
#### SOLUZIONE
- **Raccoglitore** di progetti
- Gestisce le dipendenze dei vari progetti e le loro varie configurazioni 
- Estensione `.sln`
{{% /callout %}}

{{% /col %}}

{{% col %}}

{{% callout type="note" %}}
#### PROGETTO
- **Componente** di un'applicazione
- Memorizza informazioni come
  - versione di .NET utilizzata
  - elenco delle dipendenze e dei pacchetti utilizzati
  - impostazioni di compilazione
  - tipo di output della compilazione (*eseguibile, libreria, ecc...*)
- Estensione `.csproj`
{{% /callout %}}

{{% /col %}}
{{% /multicol %}}

---

```xml
<Project Sdk="Microsoft.NET.Sdk">  
    <PropertyGroup>    
        <TargetFramework>net7.0</TargetFramework>
        <OutputType>Library</OutputType>    
        <Nullable>enable</Nullable>    
        <ImplicitUsings>enable</ImplicitUsings>  
    </PropertyGroup>  

    <ItemGroup>    
        <PackageReference Include="Newtonsoft.Json" Version="13.0.3" />  
    </ItemGroup>  

    <ItemGroup>    
        <ProjectReference Include="..\MyProject.Core\MyProject.Core.csproj" /> 
    </ItemGroup>
</Project>
```

Esempio del contenuto di un **file progetto** (`.csproj`)

---

### Organizzazione dei file di un'applicazione

{{% multicol %}}
{{% col %}}
![](imgs/fileorg.png)

<small>Esempio su GitHub: https://github.com/dotnet/samples/tree/main/framework/libraries/migrate-library-csproj</small>
{{% /col %}}

{{% col %}}
- Un **file soluzione** nella root del progetto.
- Tanti file progetto discendenti della soluzione, uno per ogni modulo della mia applicazione.
- Sotto una directory `src/` inseriamo il codice sorgente della nostra applicazione (possono essere previsti più progetti sotto `src/`)
- La directory `tests/` specchia la stessa gerarchia dei file e delle cartelle di `src/`
{{% /col %}}

{{% /multicol %}}

---

### (*alcune*) Regole di CLEAN Code

{{% multicol %}}
{{% col class="col-3" %}}

![Clean Code book](imgs/cleancode.jpg)

{{% /col %}}
{{% col %}}
- Il codice si scrive in **inglese**!
- *Specify the intent*
  - i nomi delle variabili, classi, oggetti, funzioni o qualunque altra cosa di vostra creazione devono essere SIGNIFICATIVI! No `pippo`, `pluto`, `f(x)`...
- In C# si usa il **PascalCase**! 
  - `PascalCase` per nomi di classi, metodi, proprietà, interfacce, namespace
  - `camelCase` per le variabili
  - `UPPER_CASE_SNAKE_CASE` per le costanti
- Un tab (equivalente a 2 spazi o 4 spazi a seconda della configurazione dell'IDE) per le indentazioni
  - no codice inline o codice mal indentato!
- altre regole sono possono essere prese in prestito da qui: https://web.stanford.edu/class/archive/cs/cs106b/cs106b.1272/course/style_guide/
  - altre ne incontreremo strada facendo
{{% /col %}}
{{% /multicol %}}


{{% /section %}}

---

{{% section %}}

#### Parte **#02**
## **O**.**O**.**P**. - le basi

---

### Evoluzione della programmazione nel tempo

{{% multicol %}}
{{% col %}}
{{% callout %}}
#### **Fase 01** <br> Machine Lang 
(prima degli anni '50)
{{% /callout %}}

{{% /col %}}
{{% col %}}
{{% callout %}}
#### **Fase 02** <br> Assembly
(anni '50 - '60)
{{% /callout %}}

{{% /col %}}
{{% col %}}
{{% callout %}}
#### **Fase 03** <br> Linguaggio C
(anni '70 - '80)
{{% /callout %}}

{{% /col %}}
{{% col %}}
{{% callout %}}
#### **Fase 04** <br> OOP (Java, ...)
(anni '90 - '2000)
{{% /callout %}}
{{% /col %}}
{{% /multicol %}}

<br>

- Col tempo ci si è accorti che, con la crescente **potenza computazionale** dei calcolatori e la crescente **potenzialità** dei problemi risolvibili da essi, si doveva avere la possibilità di codificare la soluzione di un dato problema in un linguaggio che "trascurasse" i dettagli di **basso livello** della macchina che la eseguiva.

- Modellazione delle **entità** che costituiscono un dominio applicativo, e delle varie **relazioni** tra di loro - minimizzando la gestione di aspetti non inerenti alla risoluzione del problema.
<br>
<br>
    
> Necessità di ASTRAZIONE! 

---

## **Everything** is an **object**.

---

#01. **Everything is an object**. Un oggetto è una **entità** che fornisce operazioni per essere manipolata.

<br>

#02. Un **programma** è un *set di oggetti* che si comunicano cosa fare scambiandosi **messaggi**. Questi messaggi sono richieste per eseguire
le **operazioni fornite**.

<br>

#03. Un oggetto ha una **memoria** fatta di altri oggetti. Un oggetto è ottenuto **impacchettando altri oggetti**.

<br>

#04. Ogni oggetto è **istanza** di una **classe**. Una **classe** descrive il comportamento dei suoi oggetti.

<br>

#05. Tutti gli oggetti di una classe possono ricevere gli **stessi messaggi**. La classe indica tra le altre cose **quali operazioni** sono fornite, quindi per comunicare con un oggetto basta sapere qual è la sua classe.

---

### Qualche esempio

{{% multicol %}}
{{% col %}}
### E#00 
`ComplexNumber`
{{% /col %}}
{{% col %}}
### E#01 
`Circle`, `Square`, `Triangle`
{{% /col %}}
{{% col %}}
### E#02  
`Student`, `Professor`, `Class`
{{% /col %}}
{{% /multicol %}}

---

{{% multicol %}}
{{% col %}}

#### POV: Progettista
```csharp
namespace BlaisePascal.OOPExamples.Domain;

public class ComplexNumber
{
    public int Real { get; set; }
    public int Imaginary { get; set; }
    
    public ComplexNumber(int re, int im)
    {
        this.Real = re;
        this.Imaginary = im;
    }

    public ComplexNumber Add(ComplexNumber other)
    {
        return new ComplexNumber(
            this.Real + other.Real, 
            this.Imaginary + other.Imaginary
        );
    }

    public ComplexNumber Subtract(ComplexNumber other)
    {
        return this.Add(new ComplexNumber(
            -other.Real, 
            -other.Imaginary
        ));
    }

    public ComplexNumber Multiply(ComplexNumber other)
    {
        // Formula: (a + ib)*(c * id) = (ac - bd) + (ad + bc)*i
        int a = this.Real; int b = this.Imaginary;
        int c = other.Real; int d = other.Imaginary;
        return new ComplexNumber(a*c - b*d, a*d + b*c);
    } // [...]
}
```
{{% /col %}}
{{% col %}}
#### POV: Utilizzatore
(Cosa vede chi utilizza la libreria)
```csharp
namespace BlaisePascal.OOPExamples.Domain.UnitTests;

public class ComplexNumberTest
{
    [Fact]
    public void Constructor_SetsRealAndImaginary()
    {
        // Arrange
        var complex = new ComplexNumber(2, 3);
        // Act & Assert
        Assert.Equal(2, complex.Real);
        Assert.Equal(3, complex.Imaginary);
    }

    [Fact]
    public void Add_ReturnsSumOfRealAndImaginary()
    {
        // Arrange
        var c1 = new ComplexNumber(1, 2);
        var c2 = new ComplexNumber(3, 4);

        // Act
        var result = c1.Add(c2);

        // Assert
        Assert.Equal(4, result.Real);
        Assert.Equal(6, result.Imaginary);
    }

    [Fact]
    // [...]
}
```
{{% /col %}}
{{% /multicol %}}

---

### **4 pillars** of Object Oriented Programming

{{% multicol %}}
{{% col %}}
#### 01. Astrazione
Paradigma orientato al problem solving, prendendo le distanze da dettagli irrilevanti della macchina utilizzata.
{{% /col %}}
{{% col %}}
#### 02. Incapsulamento
Posso nascondere in una classe informazioni che non voglio rendere visibili all'esterno.
{{% /col %}}
{{% col %}}
#### 03. Ereditarietà
Proprietà e metodi possono essere ereditati di classe in classe, sovrascritti oppure estesi.
{{% /col %}}
{{% col %}}
#### 04. Polimorfismo
Lo stesso metodo o la stessa proprietà può assumere comportamenti diversi a seconda dello scenario.
{{% /col %}}
{{% /multicol %}}

{{% /section %}}