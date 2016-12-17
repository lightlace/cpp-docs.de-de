---
title: "Generic Functions (C++/CLI)"
ms.custom: na
ms.date: "12/16/2016"
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
  - "functions [C++], generic"
  - "generic methods"
  - "generics [C++], functions"
  - "methods [C++], generic"
  - "generic functions"
ms.assetid: 8e409364-58f9-4360-b486-e7d555e0c218
caps.latest.revision: 21
caps.handback.revision: "19"
ms.author: "mblome"
manager: "ghogen"
---
# Generic Functions (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine generische Funktion ist eine Funktion, die mit den beiden Typparametern deklariert wird.  Wenn sie aufgerufen werden, werden die tatsächlichen Typen anstelle der Typparameter verwendet.  
  
## Alle Plattformen  
 **Hinweise**  
  
 Diese Funktion gilt nicht auf allen Plattformen zu.  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 **Hinweise**  
  
 Diese Funktion wird in [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] nicht unterstützt.  
  
### Voraussetzungen  
 Compileroption: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 Eine generische Funktion ist eine Funktion, die mit den beiden Typparametern deklariert wird.  Wenn sie aufgerufen werden, werden die tatsächlichen Typen anstelle der Typparameter verwendet.  
  
 **Syntax**  
  
```  
[attributes] [modifiers]  
return-type identifier <type-parameter identifier(s)>  
[type-parameter-constraints clauses]  
  
([formal-parameters])  
{  
   function-body  
}  
```  
  
 **Parameter**  
  
 *attributes* \(Optional\)  
 Zusätzliche deklarative Informationen.  Weitere Informationen zu Attributen und Attributklassen, finden Sie Attribute.  
  
 *modifiers* \(optional\)  
 Ein Modifizierer für die Funktion, z St. atic. `virtual` ist nicht zulässig, da virtuelle Methoden können nicht generisch sind.  
  
 *return\-type*  
 Der von der Methode zurückgegebene Typ.  Wenn der Rückgabetyp ungültig ist, ist kein Rückgabewert erforderlich.  
  
 *identifier*  
 Den Funktionsnamen.  
  
 *type\-parameter identifier\(s\)*  
 Durch Trennzeichen getrennte Bezeichnerliste.  
  
 *formal\-parameters* \(Optional\)  
 Parameterliste.  
  
 *type\-parameter\-constraints\-clauses*  
 Dies gibt Einschränkungen auf Typen, die als Typargumente verwendet werden, und hat die Form angezeigt, die in [Constraints on Generic Type Parameters \(C\+\+\/CLI\)](../windows/constraints-on-generic-type-parameters-cpp-cli.md).  
  
 *function\-body*  
 Der Methodentext, die die Typparameterbezeichner verweist.  
  
 **Hinweise**  
  
 Generische Funktionen sind die Funktionen, die mit einem generischen Typparameter deklariert werden.  Sie können Methoden in einer Klasse oder Struktur oder eigenständige Funktionen.  Eine einzelne generische Deklaration deklariert implizit eine Familie von Funktionen, die nur im Ersetzung eines anderen tatsächlichen Typs für den generischen Typparameter unterscheiden.  
  
 In [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] werden Klasse oder Strukturkonstruktoren nicht mit generischen Typparameter deklariert.  
  
 Wenn sie aufgerufen wird, wird der generische Typparameter durch einen tatsächlichen Typ ersetzt.  Der tatsächliche Typ wird explizit in Winkelstützen mit der Syntax angegeben werden, die einem Vorlagenfunktionsaufruf ähnelt.  Wenn er ohne Typparameter aufgerufen wird, versucht der Compiler, den tatsächlichen Typ aus den Parametern abzuleiten, der im Funktionsaufruf angegeben werden.  Wenn das geplante Typargument nicht von den verwendeten Parametern abgeleitet wurde werden kann, gibt der Compiler einen Fehler.  
  
### Voraussetzungen  
 Compileroption: **\/clr**  
  
### Beispiele  
 **Beispiel**  
  
 Im folgenden Codebeispiel wird eine generische Funktion.  
  
```  
// generics_generic_function_1.cpp  
// compile with: /clr  
generic <typename ItemType>  
void G(int i) {}  
  
ref struct A {  
   generic <typename ItemType>  
   void G(ItemType) {}  
  
   generic <typename ItemType>  
   static void H(int i) {}  
};  
  
int main() {  
   A myObject;  
  
   // generic function call  
   myObject.G<int>(10);  
  
   // generic function call with type parameters deduced  
   myObject.G(10);  
  
   // static generic function call  
   A::H<int>(10);  
  
   // global generic function call  
   G<int>(10);  
}  
```  
  
 **Beispiel**  
  
 Generische Funktionen können auf Grundlage Signatur oder Stelligkeit überladen werden, die Anzahl der Typparameter auf eine Funktion.  Generische Funktionen können mit nicht generischen Funktionen des gleichen Namens überladen werden, solange die Funktionen in einigen Typparametern unterscheiden.  Beispielsweise können die folgenden Funktionen überladen werden:  
  
```  
// generics_generic_function_2.cpp  
// compile with: /clr /c  
ref struct MyClass {  
   void MyMythod(int i) {}  
  
   generic <class T>   
   void MyMythod(int i) {}  
  
   generic <class T, class V>   
   void MyMythod(int i) {}  
};  
```  
  
 **Beispiel**  
  
 Im folgenden Beispiel wird eine generische Funktion, um das erste Element in einem Array zu suchen.  Es wird ein `MyClass` deklariert, das von der `MyBaseClass`\- Basisklasse erbt.  `MyClass` enthält eine generische Funktion, `MyFunction`, die eine andere generische Funktion aufruft, `MyBaseClassFunction`, in der Basisklasse.  In **main** wird die generische Funktion, `MyFunction`, mit verschiedenen Typargumente aufgerufen.  
  
```  
// generics_generic_function_3.cpp  
// compile with: /clr  
using namespace System;  
  
ref class MyBaseClass {  
protected:  
   generic <class ItemType>  
   ItemType MyBaseClassFunction(ItemType item) {  
      return item;  
   }  
};  
  
ref class MyClass: public MyBaseClass {  
public:  
   generic <class ItemType>  
   ItemType MyFunction(ItemType item) {  
      return MyBaseClass::MyBaseClassFunction<ItemType>(item);  
   }  
};  
  
int main() {  
   MyClass^ myObj = gcnew MyClass();  
  
   // Call MyFunction using an int.  
   Console::WriteLine("My function returned an int: {0}",  
                           myObj->MyFunction<int>(2003));  
  
   // Call MyFunction using a string.  
   Console::WriteLine("My function returned a string: {0}",  
   myObj->MyFunction<String^>("Hello generic functions!"));  
}  
```  
  
 **Ausgabe**  
  
  **Meine Funktion hat int zurück: 2003**  
 **Meine Funktion hat eine Zeichenfolge zurück: Hello generische Funktionen\!**   
## Siehe auch  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)   
 [Generics](../windows/generics-cpp-component-extensions.md)