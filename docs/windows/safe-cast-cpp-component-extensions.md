---
title: "safe_cast (C++ Component Extensions)"
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
  - "safe_cast"
  - "safe_cast_cpp"
  - "stdcli::language::safe_cast"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "safe_cast keyword [C++]"
ms.assetid: 4fa688bf-a8ec-49bc-a4c5-f48134efa4f7
caps.latest.revision: 26
caps.handback.revision: "24"
ms.author: "mblome"
manager: "ghogen"
---
# safe_cast (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der `safe_cast`\-Vorgang gibt im Erfolgsfall den angegebenen Ausdruck als den angegebenen Typ zurück, andernfalls wird `InvalidCastException` ausgegeben.  
  
## Alle Laufzeiten  
 \(Es gibt keine Hinweise für diese Sprachfunktion, die für alle Laufzeiten gültig sind.\)  
  
### Syntax  
  
```cpp  
  
[default]:: safe_cast<  
type-id  
>(  
expression  
)  
  
```  
  
### Parameter  
  
### Hinweise  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 `safe_cast` ermöglicht Ihnen, den Typ des angegebenen Ausdrucks zu ändern.  In Situationen, in denen Sie mit Sicherheit erwarten, dass eine Variable oder ein Parameter zu einem bestimmten Typ konvertiert werden kann, können Sie „safe\_cast“ ohne einen „try\-catch“\-Block verwenden, um während der Entwicklung Programmierfehler zu ermitteln.  Weitere Informationen finden Sie unter [Umwandlung von Typen \(C\+\+\/CX\)](http://msdn.microsoft.com/library/windows/apps/hh755802.aspx).  
  
### Syntax  
  
```cpp  
  
[default]:: safe_cast<  
type-id  
>(  
expression  
)  
  
```  
  
### Parameter  
 *type\-id*  
 Der Typ, zu dem *expression* konvertiert wird.  Ein Handle zu einem Verweis\- oder Werttyp, ein Werttyp oder ein Nachverfolgungsverweis auf einen Verweis\- oder Werttyp.  
  
 *expression*  
 Ein Ausdruck, der als ein Handle zu einem Verweis oder Werttyp ausgewertet wird, ein Werttyp oder ein Nachverfolgungsverweis auf einen Verweis\- oder Werttyp.  
  
### Hinweise  
 `safe_cast` gibt `InvalidCastException` aus, wenn es *expression* nicht zum durch *type\-id* angegebenen Typ konvertieren kann.  Geben Sie zum Abfangen von `InvalidCastException` die Compileroption [\/EH \(Ausnahmebehandlungsmodell\)](../build/reference/eh-exception-handling-model.md) an, und verwenden Sie eine „try\/catch“\-Anweisung.  
  
### Anforderungen  
 Compileroption: **\/ZW**  
  
### Beispiele  
 **Beispiel**  
  
 Im folgenden Codebeispiel wird die Verwendung von `safe_cast` mit [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] veranschaulicht.  
  
```cpp#  
// safe_cast_ZW.cpp  
// compile with: /ZW /EHsc  
  
using namespace default;  
using namespace Platform;  
  
interface class I1 {};  
interface class I2 {};  
interface class I3 {};  
  
ref class X : public I1, public I2 {};  
  
int main(Array<String^>^ args) {  
   I1^ i1 = ref new X;  
   I2^ i2 = safe_cast<I2^>(i1);   // OK, I1 and I2 have common type: X  
   // I2^ i3 = static_cast<I2^>(i1);   C2440 use safe_cast instead  
   try {  
      I3^ i4 = safe_cast<I3^>(i1);   // Fails because i1 is not derived from I3.  
   }   
   catch(InvalidCastException^ ic) {  
     wprintf(L"Caught expected exception: %s\n", ic->Message);  
   }  
}  
```  
  
 **Ausgabe**  
  
  **Erwartete Ausnahme wurde abgefangen: InvalidCastException**   
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 `safe_cast` ermöglicht Ihnen, den Ausdruckstyp zu ändern und einen überprüfbaren MISL\-Code zu generieren.  
  
### Syntax  
  
```cpp  
  
[cli]:: safe_cast<  
type-id  
>(  
expression  
)  
  
```  
  
### Parameter  
 *type\-id*  
 Ein Handle zu einem Verweis\- oder Werttyp, ein Werttyp oder ein Nachverfolgungsverweis auf einen Verweis\- oder Werttyp.  
  
 *expression*  
 Ein Ausdruck, der als ein Handle zu einem Verweis oder Werttyp ausgewertet wird, ein Werttyp oder ein Nachverfolgungsverweis auf einen Verweis\- oder Werttyp.  
  
### Hinweise  
 Der Ausdruck `safe_cast<`*type\-id*`>(`*expression*`)` konvertiert den Operandenausdruck zu einem Objekt vom Typ „type\-id“.  
  
 Der Compiler akzeptiert [static\_cast](../cpp/static-cast-operator.md) an den meisten Stellen, wo er `safe_cast` akzeptiert.  Bei `safe_cast` ist das Generieren von überprüfbarer MSIL jedoch garantiert, wobei `static_cast` eine nicht überprüfbare MSIL generieren könnte.  Weitere Informationen über überprüfbaren Code finden Sie unter [Reiner und überprüfbarer Code](../dotnet/pure-and-verifiable-code-cpp-cli.md) und [Peverify.exe \(PEVerify Tool\)](../Topic/Peverify.exe%20\(PEVerify%20Tool\).md).  
  
 Analog zu `static_cast` ruft `safe_cast` benutzerdefinierte Konvertierungen auf.  
  
 Weitere Informationen zu Umwandlungen finden Sie unter [Umwandlungsoperatoren](../cpp/casting-operators.md).  
  
 `safe_cast` wendet kein **const\_cast** \(kann **const** nicht umwandeln\) an.  
  
 `safe_cast` befindet sich im cli\-Namespace.  Weitere Informationen finden Sie unter [Platform, default, and cli Namespaces](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md).  
  
 Weitere Informationen über **safe\_cast** finden Sie unter:  
  
-   [C\-Style Casts with \/clr \(C\+\+\/CLI\)](../windows/c-style-casts-with-clr-cpp-cli.md)  
  
-   [Gewusst wie: Verwenden von safe\_cast in C\+\+\/CLI](../dotnet/how-to-use-safe-cast-in-cpp-cli.md)  
  
-   [Gewusst wie: Downcasting mit safe\_cast](../misc/how-to-downcast-with-safe-cast.md)  
  
-   [Gewusst wie: Verwenden von safe\_cast und generischen Typen](../misc/how-to-use-safe-cast-and-generic-types.md)  
  
-   [Gewusst wie: Verwenden von safe\_cast und benutzerdefinierten Konvertierungen](../misc/how-to-use-safe-cast-and-user-defined-conversions.md)  
  
-   [Gewusst wie: Verwenden von safe\_cast und Boxing](../misc/how-to-use-safe-cast-and-boxing.md)  
  
-   [Gewusst wie: Verwenden von safe\_cast und Unboxing](../misc/how-to-use-safe-cast-and-unboxing.md)  
  
### Anforderungen  
 Compileroption: **\/clr**  
  
### Beispiele  
 **Beispiel**  
  
 Ein Beispiel, in dem der Compiler `static_cast` nicht akzeptiert, `safe_cast` jedoch akzeptiert, sind Umwandlungen zwischen nicht verknüpften Schnittstellentypen.  Mit `safe_cast` stellt der Compiler keinen Konvertierungsfehler aus und führt zur Laufzeit eine Überprüfung aus, um zu ermitteln, ob die Umwandlung möglich ist.  
  
```cpp  
// safe_cast.cpp  
// compile with: /clr  
using namespace System;  
  
interface class I1 {};  
interface class I2 {};  
interface class I3 {};  
  
ref class X : public I1, public I2 {};  
  
int main() {  
   I1^ i1 = gcnew X;  
   I2^ i2 = safe_cast<I2^>(i1);   // OK, I1 and I2 have common type: X  
   // I2^ i3 = static_cast<I2^>(i1);   C2440 use safe_cast instead  
   try {  
      I3^ i4 = safe_cast<I3^>(i1);   // fail at runtime, no common type  
   }   
   catch(InvalidCastException^) {  
      Console::WriteLine("Caught expected exception");  
   }  
}  
```  
  
 **Ausgabe**  
  
  **Erwartete Ausnahme wurde abgefangen**   
## Siehe auch  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)