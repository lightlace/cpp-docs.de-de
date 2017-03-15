---
title: "Virtuelle Funktionen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Abgeleitete Klassen, Virtuelle Funktionen"
  - "Funktionen [C++], Virtuelle Funktionen"
  - "Virtuelle Funktionen"
ms.assetid: b3e1ed88-2a90-4af8-960a-16f47deb3452
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Virtuelle Funktionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine virtuelle Funktion ist eine Memberfunktion, von der Sie erwarten, dass sie in abgeleiteten Klassen neu definiert wird.  Wenn Sie mit einem Zeiger oder einem Verweis auf die Basisklasse auf ein abgeleitetes Klassenobjekt verweisen, können Sie eine virtuelle Funktion für dieses Objekt aufrufen und die Version der abgeleiteten Klasse für die Funktion ausführen.  
  
 Virtuelle Funktionen stellen sicher, dass die richtige Funktion für ein Objekt aufgerufen wird, und zwar unabhängig von dem Ausdruck, mit dem der Funktionsaufruf erfolgt.  
  
 Angenommen, eine Basisklasse enthält eine Funktion, die als [virtual](../cpp/virtual-cpp.md) deklariert wurde, und eine abgeleitete Klasse definiert die gleiche Funktion.  Die Funktion der abgeleiteten Klasse wird für Objekte der abgeleiteten Klasse aufgerufen, selbst wenn sie unter Verwendung eines Zeigers oder eines Verweises auf die Basisklasse aufgerufen wird.  Das folgende Beispiel zeigt eine Basisklasse, die eine Implementierung von der Funktion `PrintBalance` sowie von zwei abgeleiteten Klassen bereitstellt.  
  
```  
// deriv_VirtualFunctions.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
class Account {  
public:  
   Account( double d ) { _balance = d; }  
   virtual double GetBalance() { return _balance; }  
   virtual void PrintBalance() { cerr << "Error. Balance not available for base type." << endl; }  
private:  
    double _balance;  
};  
  
class CheckingAccount : public Account {  
public:  
   CheckingAccount(double d) : Account(d) {}  
   void PrintBalance() { cout << "Checking account balance: " << GetBalance() << endl; }  
};  
  
class SavingsAccount : public Account {  
public:  
   SavingsAccount(double d) : Account(d) {}  
   void PrintBalance() { cout << "Savings account balance: " << GetBalance(); }  
};  
  
int main() {  
   // Create objects of type CheckingAccount and SavingsAccount.  
   CheckingAccount *pChecking = new CheckingAccount( 100.00 ) ;  
   SavingsAccount  *pSavings  = new SavingsAccount( 1000.00 );  
  
   // Call PrintBalance using a pointer to Account.  
   Account *pAccount = pChecking;  
   pAccount->PrintBalance();  
  
   // Call PrintBalance using a pointer to Account.  
   pAccount = pSavings;  
   pAccount->PrintBalance();     
}  
```  
  
 Im vorherigen Code sind die Aufrufe `PrintBalance` identisch, mit Ausnahme des Objekts, auf das `pAccount` verweist.  Da `PrintBalance` virtuell ist, wird die Version der Funktion, die für das einzelne Objekt definiert ist, aufgerufen.  Die `PrintBalance`\-Funktion in den abgeleiteten Klassen `CheckingAccount` und `SavingsAccount` "überschreibt" die Funktion in der Basisklasse `Account`.  
  
 Wenn eine Klasse deklariert wird, die über keine überschreibende Implementierung der `PrintBalance`\-Funktion verfügt, wird die Standardimplementierung von der Basisklasse `Account` verwendet.  
  
 Funktionen in abgeleiteten Klassen überschreiben virtuelle Funktionen in Basisklassen nur, wenn ihr Typ derselbe ist.  Eine Funktion in einer abgeleiteten Klasse darf sich nicht nur durch ihren Rückgabetyp von einer virtuellen Funktion in einer Basisklasse unterscheiden. Auch die Argumentliste muss sich unterscheiden.  
  
 Wenn eine Funktion mithilfe von Zeigern oder Verweisen aufgerufen wird, gelten folgende Regeln:  
  
-   Ein Aufruf einer virtuellen Funktion wird entsprechend dem zugrunde liegenden Typ des Objekts aufgelöst, für den sie aufgerufen wird.  
  
-   Der Aufruf einer nicht virtuellen Funktion wird entsprechend dem Typ des Zeigers oder Verweises aufgelöst.  
  
 Das folgende Beispiel zeigt, wie sich virtuelle und nicht virtuelle Funktionen verhalten, wenn sie durch Zeiger aufgerufen werden:  
  
```  
// deriv_VirtualFunctions2.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
class Base {  
public:  
   virtual void NameOf();   // Virtual function.  
   void InvokingClass();   // Nonvirtual function.  
};  
  
// Implement the two functions.  
void Base::NameOf() {  
   cout << "Base::NameOf\n";  
}  
  
void Base::InvokingClass() {  
   cout << "Invoked by Base\n";  
}  
  
class Derived : public Base {  
public:  
   void NameOf();   // Virtual function.  
   void InvokingClass();   // Nonvirtual function.  
};  
  
// Implement the two functions.  
void Derived::NameOf() {  
   cout << "Derived::NameOf\n";  
}  
  
void Derived::InvokingClass() {  
   cout << "Invoked by Derived\n";  
}  
  
int main() {  
   // Declare an object of type Derived.  
   Derived aDerived;  
  
   // Declare two pointers, one of type Derived * and the other  
   //  of type Base *, and initialize them to point to aDerived.  
   Derived *pDerived = &aDerived;  
   Base    *pBase    = &aDerived;  
  
   // Call the functions.  
   pBase->NameOf();           // Call virtual function.  
   pBase->InvokingClass();    // Call nonvirtual function.  
   pDerived->NameOf();        // Call virtual function.  
   pDerived->InvokingClass(); // Call nonvirtual function.  
}  
```  
  
### Ausgabe  
  
```  
Derived::NameOf  
Invoked by Base  
Derived::NameOf  
Invoked by Derived  
```  
  
 Beachten Sie, dass unabhängig davon, ob die `NameOf`\-Funktion durch einen Zeiger auf `Base` oder einen Zeiger auf `Derived` aufgerufen wird, die Funktion für `Derived` aufgerufen wird.  Dies ruft die Funktion für `Derived` auf, da `NameOf` eine virtuelle Funktion ist und sowohl `pBase` als auch `pDerived` auf ein Objekt vom Typ `Derived` zeigen.  
  
 Da virtuelle Funktionen nur für Objekte von Klassentypen aufgerufen werden, können Sie keine globalen oder statischen Funktionen als **virtual** deklarieren.  
  
 Das Schlüsselwort **virtual** kann beim Deklarieren überschreibender Funktionen in einer abgeleiteten Klasse verwendet werden. Es ist jedoch nicht erforderlich, da Überschreibungen virtueller Funktionen immer virtuell sind.  
  
 Virtuelle Funktionen in einer Basisklasse müssen definiert werden, es sei denn, sie wurden mit *pure\-specifier* deklariert.  \(Weitere Informationen über rein virtuelle Funktionen finden Sie unter [Abstrakte Klassen](../cpp/abstract-classes-cpp.md)\).  
  
 Der Mechanismus für den virtuellen Funktionsaufruf kann unterdrückt werden, indem Sie den Funktionsnamen explizit mithilfe des Bereichsauflösungsoperators \(`::`\) qualifizieren.  Betrachten Sie das vorherige Beispiel, das die `Account`\-Klasse enthält.  Um `PrintBalance` in der Basisklasse aufrufen, verwenden Sie beispielsweise folgenden Code:  
  
```  
CheckingAccount *pChecking = new CheckingAccount( 100.00 );  
  
pChecking->Account::PrintBalance();  //  Explicit qualification.  
  
Account *pAccount = pChecking;  // Call Account::PrintBalance  
  
pAccount->Account::PrintBalance();   //  Explicit qualification.  
```  
  
 Beide Aufrufe von `PrintBalance` im vorherigen Beispiel unterdrücken den Mechanismus zum virtuellen Funktionsaufruf.  
  
## Siehe auch  
 [Zugriff auf virtuelle Funktionen](../misc/access-to-virtual-functions.md)