---
title: "&#220;bersicht &#252;ber Klassenmember"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Klassenmember"
  - "Klassenmember, Typen"
  - "Member"
  - "Member, Typen von Klassenmembern"
ms.assetid: 8802cfa9-705d-4f37-acde-245d6838010c
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# &#220;bersicht &#252;ber Klassenmember
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Klasse oder Struktur besteht aus Membern.  Die von einer Klasse ausgeführte Arbeit erfolgt über die Memberfunktionen.  Den Zustand, den sie verwaltet, wird in Datenmembern gespeichert.  Initialisierung von Membern und Bereinigungsvorgänge wie Freigeben von Arbeitsspeicher und Freigeben von Ressourcen erfolgen durch Konstruktoren.  In C\+\+11 und höher können Datenmember \(und sollten in der Regel\) beim Deklarieren initialisiert werden.  
  
## Typen von Klassenmembern  
 Eine vollständige Liste der Memberkategorien finden Sie im Folgenden:  
  
-   Spezielle Memberfunktionen  
  
-   [Memberfunktionen](../misc/member-functions-cpp.md)  
  
-   [\-Datenmember](../cpp/static-members-cpp.md) einschließlich integrierter Typen und anderer benutzerdefinierter Typen.  
  
-   Operatoren  
  
-   [Geschachtelte Klassendeklarationen](../cpp/nested-class-declarations.md) und.\)  
  
-   [Unions](../cpp/unions.md)  
  
-   [Enumerationen](../cpp/enumerations-cpp.md)  
  
-   [Bitfelder](../cpp/cpp-bit-fields.md)  
  
-   [Friends](../cpp/friend-cpp.md)  
  
-   [Aliase und Typdefinitionen](../cpp/aliases-and-typedefs-cpp.md).  
  
    > [!NOTE]
    >  Friends sind in der vorangehenden Liste inbegriffen, da sie in der Klassendeklaration enthalten sind.  Es sind jedoch keine echten Klassenmember, da sie nicht im Gültigkeitsbereich der Klasse liegen.  
  
## Beispiel für eine Klassendeklaration  
 Im folgenden Beispiel wird eine einfache Klassendeklaration dargestellt:  
  
```  
// TestRun.h  
  
class TestRun  
{  
    // Start member list.  
  
    //The class interface accessible to all callers.  
public:  
    // Use compiler-generated default constructor:  
    TestRun() = default;   
    // Don't generate a copy constructor:  
    TestRun(const TestRun&) = delete;    
    TestRun(std::string name);  
    void DoSomething();  
    int Calculate(int a, double d);  
    virtual ~TestRun();  
    enum class State { Active, Suspended };  
  
    // Accessible to this class and derived classes only.  
protected:  
    virtual void Initialize();  
    virtual void Suspend();  
    State GetState();  
  
    // Accessible to this class only.  
private:  
    // Default brace-initialization of instance members:  
    State _state{ State::Suspended };   
    std::string _testName{ "" };   
    int _index{ 0 };  
  
    // Non-const static member:  
    static int _instances;  
    // End member list.  
};  
  
// Define and initialize static member.  
int TestRun::_instances{ 0 };  
```  
  
## Memberzugriff  
 Die Member einer Klasse werden in der Memberliste deklariert.  Die Memberliste einer Klasse kann mithilfe von Schlüsselwörtern, die als Zugriffsspezifizierer bekannt sind, in beliebig viele `private`\-, `protected`\- und **public**\-Abschnitte unterteilt werden.  Ein Doppelpunkt **:** muss dem Zugriffsspezifizierer folgen.  Diese Abschnitte müssen nicht fortlaufend sein, d. h. sämtliche dieser Schlüsselwörter können möglicherweise mehrmals in der Memberliste vorkommen.  Das Schlüsselwort legt den Zugriff aller Member bis zum nächsten Zugriffsspezifizierer oder zur schließenden Klammer fest.  Weitere Informationen finden Sie unter [Memberzugriffssteuerung \(C\+\+\)](../cpp/member-access-control-cpp.md).  
  
## Statische Member  
 Ein Datenmember kann als statisch deklariert werden, was bedeutet, dass alle Objekte der Klasse auf die gleiche Kopie zugreifen.  Eine Memberfunktion kann als statisch deklariert werden. In diesem Fall kann sie nur auf statische Datenmember der Klasse zugreifen \(und weist keinen *this*\-Zeiger auf\).  Weitere Informationen finden Sie unter [Statische Datenmember](../cpp/static-members-cpp.md).  
  
## Spezielle Memberfunktionen  
 Spezielle Memberfunktionen stellen Funktionen dar, die vom Compiler automatisch bereitgestellt werden, wenn Sie sie nicht im Quellcode angeben.  
  
1.  Standardkonstruktor  
  
2.  Kopierkonstruktor  
  
3.  **\(C\+\+11\)** Bewegungskonstruktor  
  
4.  Kopierzuweisungsoperator  
  
5.  **\(C\+\+11\)** Bewegungszuweisungsoperator  
  
6.  Destruktor  
  
## Memberspezifische Initialisierung  
 Nicht statische Memberdeklaratoren können in C\+\+11 und höher Initialisierer enthalten.  
  
```  
  
class CanInit  
{  
public:  
    long num {7};       // OK in C++11  
    int k = 9;          // OK in C++11  
    static int i = 9; // Error: must be defined and initialized  
                      // outside of class declaration.  
  
    // initializes num to 7 and k to 9  
    CanInit(){}  
  
    // overwrites original initialized value of num:  
    CanInit(int val) : num(val) {}  
};  
int main()  
{  
}  
```  
  
 Wenn einem Member ein Wert in einem Konstruktor zugewiesen ist, überschreibt dieser Wert den Wert, mit dem der Member zum Zeitpunkt der Deklaration initialisiert wurde.  
  
 Es ist nur eine gemeinsame Kopie der statischen Datenmember für alle Objekte eines gegebenen Klassentyps vorhanden.  Statische Datenmember müssen definiert werden und können im Dateigültigkeitsbereich initialisiert werden.  \(Weitere Informationen zu statischen Datenmembern finden Sie unter [Statische Datenmember](../cpp/static-members-cpp.md)\). Das folgende Beispiel veranschaulicht, wie diese Initialisierungen vorgenommen werden:  
  
```  
// class_members2.cpp  
class CanInit2  
{  
public:  
    CanInit2() {} // Initializes num to 7 when new objects of type   
                 //  CanInit are created.  
    long     num {7};  
    static int i;  
    static int j;  
};  
  
// At file scope:  
  
// i is defined at file scope and initialized to 15.  
// The initializer is evaluated in the scope of CanInit.  
int CanInit2::i = 15;  
  
// The right side of the initializer is in the scope   
// of the object being initialized  
int CanInit2::j = i;  
```  
  
> [!NOTE]
>  Dem Klassennamen `CanInit2` muss `i` vorausgehen, um anzugeben, dass das definierte `i` ein Member der Klasse `CanInit2` ist.  
  
## Siehe auch  
 [Klassen und Strukturen](../cpp/classes-and-structs-cpp.md)