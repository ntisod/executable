# Executables

I den här labben ska vi lära oss om körbara filer, det som kallas för program eller ["executables"](https://en.wikipedia.org/wiki/Executable).

 Dessa består av instruktioner som skrivs i ett programmeringspråk, filerna kallas för   [källkod](https://sv.wikipedia.org/wiki/K%C3%A4llkod). Det finns olika sätt att hantera källkoden, vi ska titta på några.

## Binära

Binära körbara filer skapas genom att man [kompilerar](https://sv.wikipedia.org/wiki/Kompilator) källkoden till maskininstruktioner som sparas i en fil. I Windows känner ni igen dessa genom filändelsen exe. Vi kommer att använda programmeringsspråket C för att kompilera ett litet program.

## Skript

Skript är källkod som läses rad för rad av en [interpreter](https://en.wikipedia.org/wiki/Interpreter_(computing)) som översätter denna till maskinkod och [exekverar](https://en.wikipedia.org/wiki/Execution_(computing))  denna.

Vi använder python som programmeringsspråk för att testa skript.

## Java

Java använder en annan teknik, först kompilerar man källkoden till [bytekod](https://en.wikipedia.org/wiki/Java_bytecode), som är en binär fil med instruktioner, för att exekvera filen behövs en java interpreter, jvm, java virtual machine.


## Laborationen - förberedelser

Under laborationen ska vi testa att skapa, köra och flytta skript, binära filer och java program mellan er windowsdator och en virtuell linuxmaskin.

### Installationer på er windowsdator

#### Python
Ni måste installera python på er windowsdator. Ni hittar python [här](https://www.python.org/). Installera 2.17.12 som kommer att vara kompatibel med vår gamla linuxserver.

#### Java

Ni måste installera JRE, JaveRuntimeEnviorment. Det borde redan vara installerad på er dator. Öppna en terminal och skriv java, verkar det som att det är installerad så är ni klara. Annars gå [hit](http://www.java.com/en/download/windows_ie.jsp) och  följ instruktionerna.


#### linuxserver

Ni behöver en linuxmaskin för att testa på, skapa en ny genom att klona det här projektet, det följer med exempelkod också.

Öppna en gitbash terminal, gå till er projektfolder, hämta hem det här projektet med

```bash
$ git clone https://github.com/ntisod/executable.git
```

Förflytta er till den nyligen skapade foldern Executable och starta servern med `vagrant up` och logga in med `vagrant ssh`


python och gcc(för att kompilera c program) är redan installerad. Däremot måste vi installerad JDK, JavaDevelopmentKit för att kunna skapa java bytekod. För att göra det behöver vi programmet javac, ubuntu är snäll med oss om vi försöker starta javac i terminalen med

```
vagrant@precise32:~$ javac
The program 'javac' can be found in the following packages:
 * default-jdk
 * ecj
 * gcj-4.6-jdk
 * openjdk-6-jdk
 * gcj-4.5-jdk
 * openjdk-7-jdk
Try: sudo apt-get install <selected package>
```
aah det är inte installerat, vi installerar det första alternativet
men först uppdaterar vi våra förrådslistor
```
vagrant@precise32:~$ sudo apt-get update
```
och nu installera
```
vagrant@precise32:~$ sudo apt-get install default-jdk
```

## Nu är det klart!
På lektionen testar vi att kompilera och flytta program mellan maskinerna.

/happy hacking
