---
title: "delegate (Komponentenerweiterungen f&#252;r C++)"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "delegate_cpp"
  - "delegate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "delegate-Schlüsselwort [C++]"
ms.assetid: 03caf23d-7873-4a23-9b34-becf42aaf429
caps.latest.revision: 26
caps.handback.revision: "24"
ms.author: "mblome"
manager: "ghogen"
---
# delegate (Komponentenerweiterungen f&#252;r C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Deklariert einen Typ, der einen Funktionszeiger darstellt.  
  
## Alle Laufzeiten  
 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] und Common Language Runtime unterstützen Delegaten.  
  
### Hinweise  
 `delegate` ist ein kontextbezogenes Schlüsselwort.  Weitere Informationen finden Sie unter [Kontextbezogene Schlüsselwörter](../windows/context-sensitive-keywords-cpp-component-extensions.md).  
  
 Um zur Kompilierungszeit zu erkennen, ob ein Typ ein Delegat ist, verwenden Sie das `__is_delegate()`\-Typmerkmal.  Weitere Informationen finden Sie unter [Compiler Support for Type Traits](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
## Windows\-Runtime  
 C\+\+\/CX unterstützen Delegaten mit der folgenden Syntax.  
  
### Syntax  
  
```cpp  
  
access delegate return-type delegate-type-identifier ([ parameters ])  
```  
  
### Parameter  
 *access*  
 \(optional\) Der Zugriff des Delegaten, der `public` \(Standard\) oder `private` sein kann.  Der Funktionsprototyp kann auch mit den Schlüsselwörtern `const` oder `volatile` qualifiziert werden.  
  
 *return\-type*  
 Der Rückgabetyp des Funktionsprototypen.  
  
 *delegate\-type\-identifier*  
 Der Name des deklarierten Delegatentyps.  
  
 *parameters*  
 \(Optional\) Die Typen und die Bezeichner des Funktionsprototyps.  
  
### Hinweise  
 Verwenden Sie *delegate\-type\-identifier*, um ein Ereignis mit dem gleichen Prototyp wie der Delegat zu deklarieren.  Weitere Informationen finden Sie unter [Delegaten \(C\+\+\/CX\)](../Topic/Delegates%20\(C++-CX\).md).  
  
### Voraussetzungen  
 Compileroption: **\/ZW**  
  
## Common Language Runtime  
 Die Common Language Runtime unterstützt Delegaten mit der folgenden Syntax.  
  
### Syntax  
  
```cpp  
  
access delegate function_declaration  
```  
  
### Parameter  
 *access*  
 \(optional\) Der Zugriff des Delegaten außerhalb der Assembly kann öffentlich oder privat sein.  Die Standardeinstellung ist "privat".  Innerhalb einer Klasse kann ein Delegat jede Zugriffen aufweisen.  
  
 *function\_declaration*  
 Die Signatur der Funktion, die an den Delegaten gebunden werden kann.  Der Rückgabetyp eines Delegaten kann entweder verwalteter Typ sein.  Aus Kompatibilitätsgründen wird empfohlen, dass der Rückgabetyp eines Delegaten ein CLS\-Typ ist.  
  
 Um einen ungebundenen Delegaten definieren, sollte der erste Parameter in *function\_declaration* der Typ des `this` Zeigers für das Objekt sein.  Weitere Informationen finden Sie unter [Nicht gebundene Delegate](../misc/unbound-delegates.md).  
  
### Hinweise  
 Delegaten sind Multicastdelegaten: Der "Funktionszeiger" kann an eine oder mehrere Methoden innerhalb einer verwalteten Klasse gebunden werden.  Das **delegate**\-Schlüsselwort definiert einen Multicastdelegattyp mit einer bestimmten Methodensignatur.  
  
 Ein Delegat kann auch an eine Methode einer Wertklasse, wie eine statische Methode gebunden werden.  
  
 Ein Delegat weist folgende Merkmale auf:  
  
-   Es erbt von **System::MulticastDelegate**.  
  
-   Er verfügt über einen Konstruktor, der zwei Argumente akzeptiert: Ein Zeiger auf eine verwaltete Klasse oder **NULL** \(im Fall der Bindung an eine statische Methode\) und eine vollständig qualifizierte Methode des angegebenen Typs.  
  
-   Er verfügt über eine Methode mit dem Namen `Invoke`, deren Signatur der deklarierten Signatur des Delegaten entspricht.  
  
 Wenn ein Delegat aufgerufen wird, werden die Funktionen in der Reihenfolge aufgerufen, in der sie angefügt wurden.  
  
 Der Rückgabewert eines Delegaten ist der Rückgabewert der zuletzt angefügten Memberfunktion.  
  
 Delegaten dürfen nicht überladen werden.  
  
 Delegaten können gebunden oder ungebunden sein.  
  
 Wenn Sie einen gebundenen Delegaten instanziieren, ist das erste Argument ein Objektverweis.  Das zweite Argument einer Delegatinstanziierung ist entweder die Adresse einer Methode eines verwalteten Klassenobjekts oder ein Zeiger auf eine Methode eines Werttyps.   Das zweite Argument einer Delegatinstanziierung muss die Methode mit der vollständigen Syntax des Klassenbereichs benennen und den AddressOf\-Operator anwenden.  
  
 Wenn Sie einen ungebundenen Delegaten instanziieren, ist das erste Argument entweder die Adresse einer Methode eines verwalteten Klassenobjekts oder ein Zeiger auf eine Methode eines Werttyps.   Das Argument muss die Methode mit der vollständigen Syntax des Klassenbereichs benennen und den AdressOf\-Operator anwenden.  
  
 Wenn Sie einen Delegaten zu einer statischen oder globalen Funktion erstellen, ist nur ein Parameter erforderlich: Die Funktion \(optional die Adresse der Funktion\).  
  
 Weitere Informationen zu Delegaten finden Sie unter  
  
-   [Nicht gebundene Delegate](../misc/unbound-delegates.md)  
  
-   [Gewusst wie: Definieren und Verwenden von Delegaten](../dotnet/how-to-define-and-use-delegates-cpp-cli.md)  
  
-   [Delegat zu einem Member einer Wertklasse](../misc/how-to-associate-delegates-to-members-of-a-value-class.md)  
  
-   [Delegat einer nicht verwalteten Funktion](../misc/how-to-associate-delegates-to-unmanaged-functions.md)  
  
-   [Zusammengesetzte Delegaten](../misc/how-to-compose-delegates.md)  
  
-   [Gewusst wie: Übergeben eines Delegaten an eine native Funktion, die einen Funktionszeiger erwartet](../misc/how-to-pass-a-delegate-hat-to-a-native-function-expecting-a-function-pointer.md)  
  
-   [Generic Delegates \(Visual C\+\+\)](../windows/generic-delegates-visual-cpp.md)  
  
### Voraussetzungen  
 Compileroption: **\/clr**  
  
### Beispiele  
 **Beispiel**  
  
 Im folgenden Beispiel wird gezeigt, wie Delegaten deklariert, initialisiert und aufgerufen werden.  
  
```cpp  
// mcppv2_delegate.cpp  
// compile with: /clr  
using namespace System;  
  
// declare a delegate  
public delegate void MyDel(int i);  
  
ref class A {  
public:  
   void func1(int i) {  
      Console::WriteLine("in func1 {0}", i);  
   }  
  
   void func2(int i) {  
      Console::WriteLine("in func2 {0}", i);  
   }  
  
   static void func3(int i) {  
      Console::WriteLine("in static func3 {0}", i);  
   }  
};  
  
int main () {  
   A ^ a = gcnew A;  
  
   // declare a delegate instance  
   MyDel^ DelInst;  
  
   // test if delegate is initialized  
   if (DelInst)  
      DelInst(7);  
  
   // assigning to delegate  
   DelInst = gcnew MyDel(a, &A::func1);  
  
   // invoke delegate  
   if (DelInst)  
      DelInst(8);  
  
   // add a function  
   DelInst += gcnew MyDel(a, &A::func2);  
  
   DelInst(9);  
  
   // remove a function  
   DelInst -= gcnew MyDel(a, &A::func1);  
  
   // invoke delegate with Invoke  
   DelInst->Invoke(10);  
  
   // make delegate to static function  
   MyDel ^ StaticDelInst = gcnew MyDel(&A::func3);  
   StaticDelInst(11);  
}  
```  
  
 **Ausgabe**  
  
  **in func1 8**  
 **in func1 9**  
 **in func2 9**  
 **in func2 10**  
 **in static func3 11**   
## Siehe auch  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)