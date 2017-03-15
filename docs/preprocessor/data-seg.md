---
title: "data_seg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "data_seg_CPP"
  - "vc-pragma.data_seg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "data_seg-Pragma"
  - "Pragmas, data_seg"
ms.assetid: 65c66466-4c98-494f-93af-106beb4caf78
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# data_seg
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt das Datensegment an, in dem initialisierte Variablen in der OBJ\-Datei gespeichert werden.  
  
## Syntax  
  
```  
  
#pragma data_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## Hinweise  
 Die Ausdrücke *Segment* und *Abschnitt* sind in diesem Thema gleichbedeutend.  
  
 OBJ\-Dateien können mit der [dumpbin](../build/reference/dumpbin-command-line.md)\-Anwendung angezeigt werden.  Das Standardsegment für initialisierte Variablen in der OBJ\-Datei ist ".data".  Nicht initialisierte Variablen werden als mit Null initialisiert behandelt und in ".bss" gespeichert.  
  
 **data\_seg** ohne Parameter setzt das Segment auf ".data" zurück.  
  
 **push**\(optional\)  
 Legt einen Datensatz auf den internen Compilerstapel.  Ein **push** kann einen *identifier* und einen *segment\-name* haben.  
  
 **pop** \(optional\)  
 Entfernt einen Datensatz von der obersten Position des internen Compilerstapels.  
  
 *identifier* \(optional\)  
 Bei Verwendung mit **push** wird dem Datensatz im internen Compilerstapel ein Name zugewiesen.  Bei Verwendung mit **pop** werden Datensätze vom internen Stapel geholt, bis *identifier* entfernt wird. Wenn *identifier* im internen Stapel nicht gefunden wird, wird kein Element vom Stapel geholt.  
  
 *identifier* ermöglicht, mehrere Datensätze mit einem einzelnen **pop**\-Befehl zu entfernen.  
  
 *"segment\-name"*\(optional\)  
 Der Name eines Segments*.* Bei Verwendung mit **pop** wird das Element vom Stapel geholt und *segment\-name* wird zum aktiven Segmentnamen.  
  
 *"segment\-class"* \(optional\)  
 Zum Gewährleisten der Kompatibilität mit C\+\+ vor Version 2.0 eingeführt.  Wird ignoriert.  
  
## Beispiel  
  
```  
// pragma_directive_data_seg.cpp  
int h = 1;                     // stored in .data  
int i = 0;                     // stored in .bss  
#pragma data_seg(".my_data1")  
int j = 1;                     // stored in "my_data1"  
  
#pragma data_seg(push, stack1, ".my_data2")     
int l = 2;                     // stored in "my_data2"  
  
#pragma data_seg(pop, stack1)   // pop stack1 off the stack  
int m = 3;                     // stored in "stack_data1"  
  
int main() {  
}  
```  
  
 Die Daten, die mithilfe von **data\_seg** zugeordnet werden, halten keine Informationen über den Speicherort bereit.  
  
 Eine Liste der Namen, die Sie beim Erstellen eines Abschnitts nicht verwenden sollten, finden Sie unter [\/SECTION](../build/reference/section-specify-section-attributes.md).  
  
 Sie können auch Abschnitte für const\-Variablen \([const\_seg](../preprocessor/const-seg.md)\) nicht initialisierte Daten \([bss\_seg](../preprocessor/bss-seg.md)\) und Funktionen \([code\_seg](../preprocessor/code-seg.md)\) angeben.  
  
## Siehe auch  
 [Pragma\-Direktiven und das \_\_Pragma\-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)