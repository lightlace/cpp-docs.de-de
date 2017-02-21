---
title: "section | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "section_CPP"
  - "vc-pragma.section"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Pragmas, section"
  - "section-Pragma"
ms.assetid: c67215e9-2c4a-4b0f-b691-2414d2e2d96f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# section
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Erstellt einen Abschnitt in einer OBJ\-Datei.  
  
## Syntax  
  
```  
  
#pragma section( "section-name" [, attributes] )  
```  
  
## Hinweise  
 Die Ausdrücke *Segment* und *Abschnitt* sind in diesem Thema gleichbedeutend.  
  
 Sobald ein Abschnitt definiert wurde, bleibt er für den Rest der Kompilierung gültig.  Sie müssen jedoch [\_\_declspec\(allocate\)](../cpp/allocate.md) verwenden, da sonst nichts in den Abschnitt eingefügt wird.  
  
 *section\-name* ist ein erforderlicher Parameter, der den Namen des Abschnitts darstellt.  Der Name darf keinem Standard\-Abschnittsnamen ähneln.  Eine Liste der Namen, die Sie beim Erstellen eines Abschnitts nicht verwenden sollten, finden Sie unter [\/SECTION](../build/reference/section-specify-section-attributes.md).  
  
 `attributes` ist ein optionaler Parameter, der aus einem oder mehreren durch Kommas getrennten Attributen besteht, die Sie dem Abschnitt zuweisen möchten.  Mögliche `attributes`\-Parameter sind:  
  
 **read**  
 Ermöglicht Lesevorgänge für Daten.  
  
 **write**  
 Ermöglicht Schreibvorgänge für Daten.  
  
 **execute**  
 Ermöglicht die Ausführung von Code.  
  
 **shared**  
 Gibt den Abschnitt für alle Prozesse frei, die das Image laden.  
  
 **nopage**  
 Markiert den Abschnitt als nicht auslagerbar; nützlich für Win32\-Gerätetreiber.  
  
 **nocache**  
 Markiert den Abschnitt als nicht zwischenspeicherbar; nützlich für Win32\-Gerätetreiber.  
  
 **discard**  
 Markiert den Abschnitt als entfernbar; nützlich für Win32\-Gerätetreiber.  
  
 **remove**  
 Markiert den Abschnitt als nicht speicherresident; nur virtuelle Gerätetreiber \(V*x*D\).  
  
 Wenn Sie keine Attribute angeben, enthält der Abschnitt Lese\- und Schreibattribute.  
  
## Beispiel  
 Im folgenden Beispiel identifiziert die erste Anweisung den Abschnitt und seine Attribute.  Die Ganzzahl `j` wird nicht in `mysec` eingefügt, da sie nicht mit `__declspec(allocate)` deklariert wurde. `j` wird in den Datenbereich eingefügt.  Die Ganzzahl `i` wird aufgrund ihres `__declspec(allocate)`\-Speicherklassenattributs in `mysec` eingefügt.  
  
```  
// pragma_section.cpp  
#pragma section("mysec",read,write)  
int j = 0;  
  
__declspec(allocate("mysec"))  
int i = 0;  
  
int main(){}  
```  
  
## Siehe auch  
 [Pragma\-Direktiven und das \_\_Pragma\-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)