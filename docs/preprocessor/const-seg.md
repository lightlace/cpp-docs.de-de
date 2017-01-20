---
title: "const_seg"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.const_seg"
  - "const_seg_CPP"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "const_seg-Pragma"
  - "Pragmas, const_seg"
ms.assetid: 1eb58ee2-fb0e-4a39-9621-699c8f5ef957
caps.latest.revision: 12
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# const_seg
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt das Segment an, in dem [const](../cpp/const-cpp.md)\-Variablen in der OBJ\-Datei gespeichert werden.  
  
## Syntax  
  
```  
#pragma const_seg ( [ [ { push | pop}, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## Hinweise  
 Die Ausdrücke *Segment* und *Abschnitt* sind in diesem Thema gleichbedeutend.  
  
 OBJ\-Dateien können mit der [dumpbin](../build/reference/dumpbin-command-line.md)\-Anwendung angezeigt werden.  Das Standardsegment in der OBJ\-Datei für `const`\-Variablen ist .rdata.  Einige `const`\-Variablen, z. B. Skalare, sind automatisch im Codestream enthalten.  Inlinecode erscheint nicht in .rdata.  
  
 Das Definieren eines Objekts, das eine dynamische Initialisierung in einem `const_seg` benötigt, führt zu einem nicht definierten Verhalten.  
  
 `#pragma const_seg` ohne Parameter setzt das Segment auf .rdata zurück.  
  
 `push` \(optional\)  
 Legt einen Datensatz auf den internen Compilerstapel.  Ein `push` kann über einen `identifier` und einen `segment-name` verfügen.  
  
 `pop` \(optional\)  
 Entfernt einen Datensatz von der obersten Position des internen Compilerstapels.  
  
 `identifier` \(optional\)  
 Bei Verwendung mit `push` wird dem Datensatz im internen Compilerstapel ein Name zugewiesen.  Bei Verwendung mit `pop` werden Datensätze vom internen Stapel geholt, bis `identifier` entfernt wird. Wenn `identifier` im internen Stapel nicht gefunden wird, wird kein Element vom Stapel geholt.  
  
 `identifier` ermöglicht, mehrere Datensätze mit einem `pop`\-Befehl zu entfernen.  
  
 "`segment-name`" \(optional\)  
 Der Name eines Segments.  Bei Verwendung mit `pop` wird das Element vom Stapel geholt und `segment-name` wird zum aktiven Segmentnamen.  
  
 "`segment-class`" \(optional\)  
 Zum Gewährleisten der Kompatibilität mit C\+\+ vor Version 2.0 eingeführt.  Wird ignoriert.  
  
## Beispiel  
  
```  
// pragma_directive_const_seg.cpp  
// compile with: /EHsc  
#include <iostream>  
  
const int i = 7;               // inlined, not stored in .rdata  
const char sz1[]= "test1";     // stored in .rdata  
  
#pragma const_seg(".my_data1")  
const char sz2[]= "test2";     // stored in .my_data1  
  
#pragma const_seg(push, stack1, ".my_data2")  
const char sz3[]= "test3";     // stored in .my_data2  
  
#pragma const_seg(pop, stack1) // pop stack1 from stack  
const char sz4[]= "test4";     // stored in .my_data1  
  
int main() {  
    using namespace std;  
   // const data must be referenced to be put in .obj  
   cout << sz1 << endl;  
   cout << sz2 << endl;  
   cout << sz3 << endl;  
   cout << sz4 << endl;  
}  
```  
  
  **test1**  
**test2**  
**test3**  
**test4**   
## Kommentare  
 Eine Liste der Namen, die Sie beim Erstellen eines Abschnitts nicht verwenden sollten, finden Sie unter [\/SECTION](../build/reference/section-specify-section-attributes.md).  
  
 Sie können auch Abschnitte für initialisierte Daten \([data\_seg](../preprocessor/data-seg.md)\) nicht initialisierte Daten \([bss\_seg](../preprocessor/bss-seg.md)\) und Funktionen \([code\_seg](../preprocessor/code-seg.md)\) angeben.  
  
## Siehe auch  
 [Pragma\-Direktiven und das \_\_Pragma\-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)