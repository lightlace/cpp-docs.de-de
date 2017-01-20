---
title: "abstract  (C++ Component Extensions)"
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
  - "abstract"
  - "abstract_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "abstract keyword [C++]"
ms.assetid: cbae3408-0378-4ac8-b70d-c016b381a6d5
caps.latest.revision: 21
caps.handback.revision: "21"
ms.author: "mblome"
manager: "ghogen"
---
# abstract  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das `abstract`\-Schlüsselwort nimmt eine der folgenden Deklarationen vor:  
  
-   Ein Typ kann als Basistyp verwendet werden, aber der Typ selbst kann nicht instanziiert werden.  
  
-   Eine Typmemberfunktion kann nur in einem abgeleiteten Typ definiert werden.  
  
## Alle Plattformen  
 **Syntax**  
  
```  
  
class-declaration class-identifier abstract {}  
virtual return-type member-function-identifier() abstract ;  
  
```  
  
 **Hinweise**  
  
 Die erste Beispielsyntax deklariert eine Klasse als abstrakt.  Die *class\-declaration*\-Komponente kann entweder eine systemeigene C\+\+\-Deklaration \(`class` oder `struct`\) oder eine C\+\+\-Erweiterungsdeklaration \(`ref class` oder `ref struct`\) sein, wenn die Compileroption **\/ZW** oder **\/clr** angegeben wird.  
  
 Die zweite Beispielsyntax deklariert eine virtuelle Memberfunktion als abstrakt.  Das Deklarieren einer Funktion als abstrakt ist mit dem Deklarieren als rein virtuelle Funktion identisch.  Das Deklarieren einer Memberfunktion als abstrakt bewirkt, dass auch die einschließende Klasse als abstrakt deklariert wird.  
  
 Das `abstract`\-Schlüsselwort wird in systemeigenem und plattformspezifischem Code unterstützt, d. h. es kann mit oder ohne Compileroption **\/ZW** oder **\/clr** kompiliert werden.  
  
 Sie können mit der `__is_abstract(``type``)`\-Typeigenschaft zum Zeitpunkt der Kompilierung ermitteln, ob ein Typ abstrakt ist.  Weitere Informationen finden Sie unter [Compiler Support for Type Traits](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
 Das `abstract`\-Schlüsselwort ist ein kontextbezogener Überschreibungsspezifizierer.  Weitere Informationen zu kontextbezogenen Schlüsselwörtern finden Sie unter [Kontextbezogene Schlüsselwörter](../windows/context-sensitive-keywords-cpp-component-extensions.md).  Weitere Informationen zu Überschreibungsspezifizierern finden Sie unter [Gewusst wie: Deklarieren Sie Überschreibungs\-Spezifizierer in systemeigenen Kompilierungen](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 Weitere Informationen finden Sie unter [Verweisklassen und Strukturen \(C\+\+\/CX\)](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx).  
  
### Anforderungen  
 Compileroption: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
  
### Anforderungen  
 Compileroption: **\/clr**  
  
### Beispiele  
 **Beispiel**  
  
 Das folgende Codebeispiel generiert einen Fehler, da Klasse `X` als `abstract` gekennzeichnet ist.  
  
```  
// abstract_keyword.cpp  
// compile with: /clr  
ref class X abstract {  
public:  
   virtual void f() {}  
};  
  
int main() {  
   X ^ MyX = gcnew X;   // C3622  
}  
```  
  
 **Beispiel**  
  
 Das folgende Codebeispiel generiert einen Fehler, da es eine systemeigene Klasse instanziiert, die als `abstract` gekennzeichnet ist.  Dieser Fehler tritt mit und ohne Compileroption **\/clr** auf.  
  
```  
// abstract_keyword_2.cpp  
class X abstract {  
public:  
   virtual void f() {}  
};  
  
int main() {  
   X * MyX = new X; // C3622: 'X': a class declared as 'abstract'  
                    // cannot be instantiated. See declaration of 'X'}  
  
```  
  
 **Beispiel**  
  
 Das folgende Codebeispiel generiert einen Fehler, da Funktion `f` eine Definition enthält, aber als `abstract` gekennzeichnet ist.  Die letzte Anweisung im Beispiel zeigt, dass das Deklarieren einer abstrakten virtuellen Funktion dem Deklarieren einer rein virtuellen Funktion entspricht.  
  
```  
// abstract_keyword_3.cpp  
// compile with: /clr  
ref class X {  
public:  
   virtual void f() abstract {}   // C3634  
   virtual void g() = 0 {}   // C3634  
};  
```  
  
## Siehe auch  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)