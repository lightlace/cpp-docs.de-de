---
title: "Gewusst wie: Migrieren auf /clr:safe (C++/CLI)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/clr-Compileroption [C++], Migrieren zu /clr:safe"
  - "Migration [C++], Überprüfbare Assemblys"
  - "Aktualisieren von Visual C++-Anwendungen, Überprüfbare Assemblys"
  - "Überprüfbare Assemblys [C++], Migrieren zu"
ms.assetid: 75f9aae9-1dcc-448a-aa11-2d96f972f9d2
caps.latest.revision: 15
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Migrieren auf /clr:safe (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ kann unter Verwendung von **\/clr:safe** überprüfbaren Komponenten generieren. Dadurch gibt der Compiler für jedes nicht überprüfbare Codekonstrukt einen Fehler aus.  
  
## Hinweise  
 In den folgenden Fällen werden Überprüfbarkeitsfehler ausgegeben:  
  
-   Systemeigene Typen.  Auch wenn sie nicht verwendet wird, verhindert eine Deklaration systemeigener Klassen, Strukturen, Zeiger oder Arrays die Kompilierung.  
  
-   Globale Variablen  
  
-   Funktionsaufrufe in eine nicht verwaltete Bibliothek, einschließlich der Common Language Runtime\-Funktionsaufrufe  
  
-   Eine überprüfbare Funktion darf keinen [static\_cast\-Operator](../cpp/static-cast-operator.md) für die Abwärtskonvertierung enthalten.  Der [static\_cast\-Operator](../cpp/static-cast-operator.md) kann zur Typkonvertierung zwischen primitiven Typen verwendet werden, für die Abwärtskonvertierung muss jedoch [safe\_cast](../windows/safe-cast-cpp-component-extensions.md) oder eine Umwandlung im C\-Format \(als [safe\_cast](../windows/safe-cast-cpp-component-extensions.md) implementiert\) verwendet werden.  
  
-   Eine überprüfbare Funktion darf keinen [reinterpret\_cast\-Operator](../cpp/reinterpret-cast-operator.md) \(oder eine entsprechende Umwandlung im C\-Format\) enthalten.  
  
-   Eine überprüfbare Funktion kann keine Arithmetik mit einem [interior\_ptr \(C\+\+\/CLI\)](../windows/interior-ptr-cpp-cli.md) ausführen.  Es sind nur Zeigerzuweisungen und \-dereferenzierungen zulässig.  
  
-   Eine überprüfbare Funktion darf lediglich Zeiger auf Referenztypen auslösen oder abfangen, daher müssen Werttypen vor dem Auslösen geschachtelt werden.  
  
-   Eine überprüfbare Funktion darf lediglich überprüfbare Funktionen aufrufen \(CRT\-Aufrufe sind daher nicht zulässig, denn sie enthalten `AtEntry`\/`AtExit`, weshalb globale Konstruktoren nicht erlaubt sind\).  
  
-   Eine überprüfbare Klasse kann nicht <xref:System.Runtime.InteropServices.LayoutKind> verwenden.  
  
-   Beim Erstellen einer EXE\-Datei dürfen in einer Hauptfunktion keine Parameter deklariert werden, sodass <xref:System.Environment.GetCommandLineArgs*> zum Abrufen der Befehlszeilenargumente verwendet werden muss.  
  
-   Ausführen eines nicht virtuellen Aufrufs einer virtuellen Funktion.  Beispiel:  
  
    ```  
    // not_verifiable.cpp  
    // compile with: /clr  
    ref struct A {  
       virtual void Test() {}  
    };  
  
    ref struct B : A {};  
  
    int main() {  
       B^ b1 = gcnew B;  
       b1->A::Test();   // Non-virtual call to virtual function  
    }  
    ```  
  
 Auch die folgenden Schlüsselwörter sind aus überprüfbarem Code auszuschließen:  
  
-   Pragmas [unmanaged](../preprocessor/managed-unmanaged.md) und [pack](../preprocessor/pack.md)  
  
-   [\_\_declspec](../cpp/declspec.md)\-Modifizierer [naked](../cpp/naked-cpp.md) und [align](../cpp/align-cpp.md)  
  
-   [\_\_asm](../assembler/inline/asm.md)  
  
-   [\_\_based](../cpp/based-grammar.md)  
  
-   [\_\_try](../cpp/try-except-statement.md) und `__except`  
  
## Siehe auch  
 [Reiner und überprüfbarer Code](../dotnet/pure-and-verifiable-code-cpp-cli.md)