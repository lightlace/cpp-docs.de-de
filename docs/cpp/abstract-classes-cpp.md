---
title: "Abstrakte Klassen (C++)"
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
  - "Abstrakte Klassen"
  - "Basisklassen, Abstrakte Klassen"
  - "Klassen [C++], abstract"
  - "Abgeleitete Klassen, Abstrakte Klassen"
ms.assetid: f0c5975b-39de-4d68-9640-6ce57f4632e6
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Abstrakte Klassen (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Abstrakte Klassen fungieren als Ausdrücke allgemeiner Konzepte, von denen spezifischere Klassen abgeleitet werden können.  Sie können kein Objekt vom Typ einer abstrakten Klasse erstellen. Sie können jedoch Zeiger und Verweise auf Typen einer abstrakten Klasse verwenden.  
  
 Eine Klasse, die mindestens eine rein virtuelle Funktion enthält, wird als abstrakte Klasse angesehen.  Klassen, die von der abstrakten Klasse abgeleitet sind, müssen die rein virtuelle Funktion implementieren, um nicht selbst als abstrakte Klasse angesehen zu werden.  
  
 Eine virtuelle Funktion wird als "rein" deklariert, indem die *pure\-specifier*\-Syntax \(beschrieben unter [Klassenprotokollimplementierung](assetId:///a319f1b3-05e8-400e-950a-1ca6eb105ab5)\) verwendet wird.  Betrachten Sie das unter [Virtuelle Funktionen](../cpp/virtual-functions.md) dargestellte Beispiel.  Mit der `Account`\-Klasse soll eine allgemeine Funktionalität gewährleistet werden, aber Objekte vom Typ `Account` sind zu allgemein, um von Nutzen zu sein.  Daher ist `Account` ein guter Kandidat für eine abstrakte Klasse:  
  
```  
// deriv_AbstractClasses.cpp  
// compile with: /LD  
class Account {  
public:  
   Account( double d );   // Constructor.  
   virtual double GetBalance();   // Obtain balance.  
   virtual void PrintBalance() = 0;   // Pure virtual function.  
private:  
    double _balance;  
};  
  
```  
  
 Diese Deklaration unterscheidet sich von der vorherigen einzig darin, dass `PrintBalance` mit dem reinen Bezeichner \(`= 0`\) deklariert wird.  
  
## Einschränkungen für abstrakte Klassen  
 Abstrakte Klassen können nicht verwendet werden für:  
  
-   Variablen oder Memberdaten  
  
-   Argumenttypen  
  
-   Funktionsrückgabetypen  
  
-   Typen expliziter Konvertierungen  
  
 Eine weitere Einschränkung ist, dass, wenn der Konstruktor für eine abstrakte Klasse eine rein virtuelle Funktion entweder direkt oder indirekt aufruft, das Ergebnis nicht definiert ist.  Allerdings können Konstruktoren und Destruktoren für abstrakte Klassen andere Memberfunktionen aufrufen.  
  
 Rein virtuelle Funktionen können für abstrakte Klassen definiert werden, sie können aber nur mithilfe folgender Syntax direkt aufgerufen werden:  
  
 *abstract\-class\-name* `::` *function\-name***\( \)**  
  
 Dies ist hilfreich beim Entwerfen von Klassenhierarchien, deren Basisklasse\(\)n rein virtuelle Destruktoren enthält\/enthalten, da Basisklassendestruktoren immer beim Löschen eines Objekts aufgerufen werden.  Betrachten Sie das folgende Beispiel:  
  
```  
// Declare an abstract base class with a pure virtual destructor.  
// deriv_RestrictionsonUsingAbstractClasses.cpp  
class base {  
public:  
    base() {}  
    virtual ~base()=0;  
};  
  
// Provide a definition for destructor.  
base::~base() {}  
  
class derived:public base {  
public:  
    derived() {}  
    ~derived(){}  
};  
  
int main() {  
    derived *pDerived = new derived;  
    delete pDerived;  
}  
```  
  
 Wenn das Objekt, auf das `pDerived` zeigt, gelöscht wird, wird der Destruktor für die `derived`\-Klasse aufgerufen, und dann wird der Destruktor für die `base`\-Klasse aufgerufen.  Die leere Implementierung für die rein virtuelle Funktion gewährleistet, dass zumindest eine gewisse Implementierung für die Funktion vorhanden ist.  
  
> [!NOTE]
>  Im vorherigen Beispiel wird die rein virtuelle Funktion `base::~base` implizit von `derived::~derived` aufgerufen.  Es ist auch möglich, rein virtuelle Funktionen explizit mithilfe eines vollqualifizierten Memberfunktionsnamens aufzurufen.  
  
## Siehe auch  
 [Vererbung](../cpp/inheritance-cpp.md)