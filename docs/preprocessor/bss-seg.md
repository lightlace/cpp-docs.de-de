---
title: "bss_seg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.bss_seg"
  - "bss_seg_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bss_seg-Pragma"
  - "Pragmas, bss_seg"
ms.assetid: 755f0154-de51-4778-97d3-c9b24e445079
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# bss_seg
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt das Segment an, in dem nicht initialisierte Variablen in der OBJ\-Datei gespeichert werden.  
  
## Syntax  
  
```  
  
#pragma bss_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## Hinweise  
 OBJ\-Dateien können mit der [dumpbin](../build/reference/dumpbin-command-line.md)\-Anwendung angezeigt werden.  Das Standardsegment für nicht initialisierte Variablen in der OBJ\-Datei ist ".bss".  In einigen Fällen kann **bss\_seg** die Ladezeiten beschleunigen, indem nicht initialisierte Daten in einen Abschnitt gruppiert werden.  
  
 **bss\_seg** ohne Parameter setzt das Segment auf ".bss" zurück.  
  
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
// pragma_directive_bss_seg.cpp  
int i;                     // stored in .bss  
#pragma bss_seg(".my_data1")  
int j;                     // stored in "my_data1"  
  
#pragma bss_seg(push, stack1, ".my_data2")     
int l;                     // stored in "my_data2"  
  
#pragma bss_seg(pop, stack1)   // pop stack1 from stack  
int m;                     // stored in "stack_data1"  
  
int main() {  
}  
```  
  
 Sie können auch Abschnitte für initialisierte Daten \([data\_seg](../preprocessor/data-seg.md)\), Funktionen \([code\_seg](../preprocessor/code-seg.md)\) und const\-Variablen \([const\_seg](../preprocessor/const-seg.md)\) angeben.  
  
 Die Daten, die mithilfe des **bss\_seg**\-Pragmas zugeordnet werden, halten keine Informationen über den Speicherort bereit.  
  
 Eine Liste der Namen, die Sie beim Erstellen eines Abschnitts nicht verwenden sollten, finden Sie unter [\/SECTION](../build/reference/section-specify-section-attributes.md).  
  
## Siehe auch  
 [Pragma\-Direktiven und das \_\_Pragma\-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)