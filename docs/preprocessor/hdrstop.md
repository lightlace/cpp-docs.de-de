---
title: "hdrstop | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "hdrstop_CPP"
  - "vc-pragma.hdrstop"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hdrstop-Pragma"
  - "Pragmas, hdrstop"
ms.assetid: 5ea8370a-10d1-4538-ade6-4c841185da0e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# hdrstop
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt Ihnen zusätzliche Kontrolle über Vorkompilierungs\-Dateinamen und über den Speicherort, an dem der Zustand der Kompilierung gespeichert wird.  
  
## Syntax  
  
```  
  
#pragma hdrstop [( "filename" )]    
```  
  
## Hinweise  
 Der *Dateiname* ist der Name der zu verwendenden oder zu erstellenden vorkompilierten Headerdatei \(je nachdem, ob [\/Yu](../build/reference/yu-use-precompiled-header-file.md) oder [\/Yc](../build/reference/yc-create-precompiled-header-file.md) angegeben ist\).  Wenn *filename* keine Pfadangabe enthält, wird davon ausgegangen, dass sich die vorkompilierte Headerdatei im selben Verzeichnis wie die Quelldatei befindet.  
  
 Wenn eine C\- oder C\+\+\-Datei ein **hdrstop**\-Pragma enthält, wenn sie mit \/Yc kompiliert wird, speichert der Compiler den Zustand der Kompilierung bis zur Position des Pragmas.  Der kompilierte Zustand von Code, der dem Pragma folgt, wird nicht gespeichert.  
  
 Verwenden Sie *filename*, um die vorkompilierte Headerdatei zu benennen, in der der kompilierte Zustand gespeichert wird.  Ein Leerzeichen zwischen **hdrstop** und *filename* ist optional.  Der Dateiname, der im Pragma **hdrstop** bezeichnet wird, ist eine Zeichenfolge und unterliegt daher den Einschränkungen jeder Zeichenfolge in C oder C\+\+.  Insbesondere ist die Einschließung in Anführungszeichen und die Verwendung von Escapezeichen \(umgekehrter Schrägstrich\) erforderlich, um Verzeichnisnamen anzugeben.  Beispiel:  
  
```  
#pragma hdrstop( "c:\\projects\\include\\myinc.pch" )  
```  
  
 Der Name der vorkompilierten Headerdatei wird gemäß den folgenden Regeln, in Rangfolge aufgelistet, bestimmt:  
  
1.  Das Argument für die \/Fp\-Compileroption  
  
2.  Das Argument *filename* für \#**Pragma hdrstop**  
  
3.  Der Basisname der Quelldatei mit einer .PCH\-Erweiterung  
  
 Wenn für die \/Yc\- und \/Yu\-Optionen weder eine der beiden Kompilierungsoptionen noch das **hdrstop** \-Pragma einen Dateinamen angeben, wird der Basisname der Quelldatei als Basisname der vorkompilierten Headerdatei verwendet.  
  
 Sie können auch Präprozessorbefehle wie folgt verwenden, um Makroersetzung auszuführen:  
  
```  
#define INCLUDE_PATH "c:\\progra~`1\\devstsu~1\\vc\\include\\"  
#define PCH_FNAME "PROG.PCH"  
.  
.  
.  
#pragma hdrstop( INCLUDE_PATH PCH_FNAME )  
```  
  
 Anhand der folgenden Regeln wird bestimmt, wo das Pragma **hdrstop**  platziert werden kann:  
  
-   Es muss außerhalb einer Daten\- oder Funktionsdeklaration oder \-definition angezeigt werden.  
  
-   Es muss in der Quelldatei, nicht in einer Headerdatei angegeben werden.  
  
## Beispiel  
  
```  
#include <windows.h>                 // Include several files  
#include "myhdr.h"  
  
__inline Disp( char *szToDisplay )   // Define an inline function  
{  
    ...                              // Some code to display string  
}  
#pragma hdrstop  
```  
  
 In diesem Beispiel erscheint das **hdrstop**\-Pragma, nachdem zwei Dateien einbezogen wurden und eine Inlinefunktion definiert wurde.  Dies erscheint auf den ersten Blick eher als eine ungewöhnliche Platzierung für das Pragma.  Berücksichtigen Sie jedoch, dass durch die Verwendung der manuellen Vorkompilierungsoptionen "\/Yc" und "\/Yu" mit dem **hdrstop**\-Pragma ganze Quelldateien, sogar Inlinecode, vorkompiliert werden können.  Mit dem Microsoft\-Compiler können nicht nur Datendeklarationen vorkompiliert werden.  
  
## Siehe auch  
 [Pragma\-Direktiven und das \_\_Pragma\-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)