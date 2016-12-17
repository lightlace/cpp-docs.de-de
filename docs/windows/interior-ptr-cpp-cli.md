---
title: "interior_ptr (C++/CLI)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "stdcli::language::interior_ptr"
  - "interior_ptr_cpp"
  - "interior_ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "interior_ptr keyword [C++]"
ms.assetid: 25160f74-569e-492d-9e3c-67ece7486baa
caps.latest.revision: 17
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# interior_ptr (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein *innerer Zeiger* deklarieren einen Zeiger in einen Verweistyp, jedoch nicht auf das Objekt selbst.  Ein innerer Zeiger kann auf einem Bezugshandle, Werttyp, eingepacktes Typhandle, Member eines verwalteten Typs oder ein Element eines verwalteten Arrays wird.  
  
## Alle Laufzeiten  
 \(Es gibt keine Hinweise für diese Sprachfunktion, die für alle Laufzeiten gültig sind.\)  
  
## Windows\-Runtime  
 \(Es gibt keine Hinweise für diese Sprachfunktion, die nur für Windows\-Runtime gelten.\)  
  
### Voraussetzungen  
 Compileroption: **\/ZW**  
  
## Common Language Runtime  
 Im folgenden Syntaxbeispiel zeigt einen inneren Zeiger.  
  
### Syntax  
  
```cpp  
cli::interior_ptr<cv_qualifier type> var = &initializer;  
```  
  
### Parameter  
 *cv\_qualifier*  
 **const** oder Qualifizierer `volatile`.  
  
 *type*  
 Der *initializer*\-Typ.  
  
 *var*  
 Der Name der Variablen `interior_ptr`.  
  
 *initializer*  
 Ein Member eines Referenztyps, des Elements eines verwalteten Arrays oder einem anderen Objekt, das auf einem systemeigenen Zeiger zuweisen können.  
  
### Hinweise  
 Ein systemeigener Zeiger ist nicht in der Lage, ein Element zu verfolgen, da sein Speicherort auf dem verwalteten Heap ändern, der von den verschobenen Instanzen des Garbage Collectors eines Objekts entsteht.  Damit ein Zeiger ordnungsgemäß die Instanz, die Common Language Runtime muss den Zeiger auf das neu positionierbare Objekt aktualisieren verweist.  
  
 `interior_ptr` stellt eine Obermenge der Funktionalität eines systemeigenen Zeiger dar.  Daher alles kann, das auf einem systemeigenen Zeiger zugewiesen werden kann, auch zugewiesen sind `interior_ptr`.  Ein innerer Zeiger ist zulässig, um den gleichen Satz von Vorgängen wie systemeigene Zeiger, einschließlich den Vergleich und Zeigerarithmetik auszuführen.  
  
 Ein innerer Zeiger kann auf dem Stapel nur deklariert werden.  Ein innerer Zeiger kann nicht als Member einer Klasse deklariert werden.  
  
 Da innere Zeiger nur vom Stapel vorhanden und nehmen die Adresse von Erträgen eines inneren Zeigers einen nicht verwalteten Zeiger.  
  
 `interior_ptr` enthält eine implizite Konvertierung in `bool`, die dessen Verwendung in Bedingungsanweisungen zulässt.  
  
 Informationen dazu, wie Sie einen inneren Zeiger, der auf ein Objekt verweist, das nicht auf dem Heap der Garbage Collection verschoben werden kann, finden Sie unter [pin\_ptr](../windows/pin-ptr-cpp-cli.md) deklariert.  
  
 `interior_ptr` befindet sich im cli\-Namespace.  Weitere Informationen finden Sie unter [Platform, default, and cli Namespaces](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md).  
  
 Weitere Informationen zum inneren Zeiger, finden Sie unter  
  
-   [How to: Declare and Use Interior Pointers and Managed Arrays \(C\+\+\/CLI\)](../windows/how-to-declare-and-use-interior-pointers-and-managed-arrays-cpp-cli.md)  
  
-   [How to: Declare Value Types with the interior\_ptr Keyword \(C\+\+\/CLI\)](../windows/how-to-declare-value-types-with-the-interior-ptr-keyword-cpp-cli.md)  
  
-   [How to: Overload Functions with Interior Pointers and Native Pointers \(C\+\+\/CLI\)](../windows/how-to-overload-functions-with-interior-pointers-and-native-pointers-cpp-cli.md)  
  
-   [How to: Declare Interior Pointers with the const Keyword \(C\+\+\/CLI\)](../windows/how-to-declare-interior-pointers-with-the-const-keyword-cpp-cli.md)  
  
### Voraussetzungen  
 Compileroption: **\/clr**  
  
### Beispiele  
 **Beispiel**  
  
 Das folgende Beispiel zeigt, wie ein innerer Zeiger in einen Verweistyp deklariert und verwendet.  
  
```cpp  
// interior_ptr.cpp  
// compile with: /clr  
using namespace System;  
  
ref class MyClass {  
public:  
   int data;  
};  
  
int main() {  
   MyClass ^ h_MyClass = gcnew MyClass;  
   h_MyClass->data = 1;  
   Console::WriteLine(h_MyClass->data);  
  
   interior_ptr<int> p = &(h_MyClass->data);  
   *p = 2;  
   Console::WriteLine(h_MyClass->data);  
  
   // alternatively  
   interior_ptr<MyClass ^> p2 = &h_MyClass;  
   (*p2)->data = 3;  
   Console::WriteLine((*p2)->data);  
}  
```  
  
 **Ausgabe**  
  
 **1**   
**2**   
**3**   
## Siehe auch  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)