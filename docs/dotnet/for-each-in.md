---
title: "for each, in"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "cliext::foreach"
  - "for"
  - "each"
  - "in"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "for-each-Schlüsselwort [C++]"
ms.assetid: 0c3a364b-2747-43f3-bb8d-b7d3b7023f79
caps.latest.revision: 24
caps.handback.revision: "22"
ms.author: "mblome"
manager: "ghogen"
---
# for each, in
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Durchläuft ein Array oder eine Auflistung.  Dieses nicht standardmäßige Schlüsselwort ist sowohl in C\+\+\/CLI und nativen C\+\+\-Projekten verfügbar.  Seine Verwendung wird jedoch nicht empfohlen.  Verwenden Sie stattdessen eine standardmäßige [Bereichsbasiert für Anweisung \(C\+\+\)](../cpp/range-based-for-statement-cpp.md)\-Methode.  
  
## Alle Laufzeiten  
 **Syntax**  
  
```  
  
        for each (type identifier in expression) {  
   statements  
}  
  
```  
  
 **Parameter**  
  
 `type`  
 Der `identifier`\-Typ.  
  
 `identifier`  
 Die Iterationsvariable, die das Auflistungselement darstellt.  Wenn `identifier` ein [Tracking Reference Operator](../windows/tracking-reference-operator-cpp-component-extensions.md) ist, können Sie das Element ändern.  
  
 `expression`  
 Ein Arrayausdruck oder eine Auflistung.  Das Auflistungselement muss zulassen, dass der Compiler es in den Typ `identifier` konvertieren kann.  
  
 `statements`  
 Eine oder mehrere auszuführende Anweisungen.  
  
 **Hinweise**  
  
 Die `for each`\-Anweisung wird zum Durchlaufen einer Auflistung verwendet.  Sie können Elemente in einer Auflistung ändern, aber keine Elemente hinzufügen oder löschen.  
  
 Die *statements* werden für jedes Element im Array oder in der Auflistung ausgeführt.  Nachdem die Iteration alle Elemente in der Auflistung durchlaufen hat, wird die Steuerung an die nächste Anweisung, die auf den `for each`\-Block folgt, übergeben.  
  
 `for each` und `in` sind [kontextbezogene Schlüsselwörter](../windows/context-sensitive-keywords-cpp-component-extensions.md).  
  
 Weitere Informationen finden Sie unter:  
  
-   [Eine STL\-Auflistung mit der for\-each\-Klausel durchlaufen](../dotnet/iterating-over-stl-collection-by-using-for-each.md)  
  
-   [Gewusst wie: Durchlaufen von Arrays mit der for\-each\-Klausel](../dotnet/how-to-iterate-over-arrays-with-for-each.md)  
  
-   [Gewusst wie: Durchlaufen einer generischen Auflistung mit der for\-each\-Klausel](../dotnet/how-to-iterate-over-a-generic-collection-with-for-each.md)  
  
-   [Gewusst wie: Durchlaufen einer benutzerdefinierten Auflistung mit der for\-each\-Klausel](../dotnet/how-to-iterate-over-a-user-defined-collection-with-for-each.md)  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
  
### Anforderungen  
 Compileroption: **\/ZW**  
  
### Beispiel  
 Dieses Beispiel zeigt, wie `for each` zum Durchlaufen einer Zeichenfolge verwendet wird.  
  
```  
// for_each_string1.cpp  
// compile with: /ZW  
#include <stdio.h>  
using namespace Platform;  
  
ref struct MyClass {  
   property String^ MyStringProperty;  
};  
  
int main() {  
   String^ MyString = ref new String("abcd");  
  
   for each ( char c in MyString )  
      wprintf("%c", c);  
  
   wprintf("/n");  
  
   MyClass^ x = ref new MyClass();  
   x->MyStringProperty = "Testing";  
  
   for each( char c in x->MyStringProperty )  
      wprintf("%c", c);  
}  
```  
  
 **Ausgabe**  
  
  **abcd**  
 **Testen**   
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **Hinweise**  
  
 Die CLR\-Syntax ist mit der **Alle Laufzeiten**\-Syntax identisch, mit folgenden Ausnahmen.  
  
 *expression*  
 Ein verwalteter Arrayausdruck oder eine Auflistung.  Das Auflistungselement muss zulassen, dass der Compiler es vom Typ <xref:System.Object> in den Typ *identifier* konvertieren kann.  
  
 *expression* wird zu einem Typ ausgewertet, der <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable`1> implementiert, oder zu einem Typ, der eine `GetEnumerator`\-Methode definiert, die entweder einen Typ zurückgibt, der <xref:System.Collections.IEnumerator> implementiert oder alle Methoden deklariert, die in `IEnumerator` definiert sind.  
  
### Anforderungen  
 Compileroption: **\/clr**  
  
### Beispiel  
 Dieses Beispiel zeigt, wie `for each` zum Durchlaufen einer Zeichenfolge verwendet wird.  
  
```  
// for_each_string2.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct MyClass {  
   property String ^ MyStringProperty;  
};  
  
int main() {  
   String ^ MyString = gcnew String("abcd");  
  
   for each ( Char c in MyString )  
      Console::Write(c);  
  
   Console::WriteLine();  
  
   MyClass ^ x = gcnew MyClass();  
   x->MyStringProperty = "Testing";  
  
   for each( Char c in x->MyStringProperty )  
      Console::Write(c);  
}  
```  
  
 **Ausgabe**  
  
  **abcd**  
 **Testen**    
## Siehe auch  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)