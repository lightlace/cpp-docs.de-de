---
title: Hdrstop | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- hdrstop_CPP
- vc-pragma.hdrstop
dev_langs: C++
helpviewer_keywords:
- hdrstop pragma
- pragmas, hdrstop
ms.assetid: 5ea8370a-10d1-4538-ade6-4c841185da0e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cf1bd1d80f692695c1cbf4ad535d2c5e759e4ea5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="hdrstop"></a>hdrstop
Gibt Ihnen zusätzliche Kontrolle über Vorkompilierungs-Dateinamen und über den Speicherort, an dem der Zustand der Kompilierung gespeichert wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
#pragma hdrstop [( "filename" )]    
```  
  
## <a name="remarks"></a>Hinweise  
 Die *Filename* ist der Name des zu verwenden, oder Erstellen der vorkompilierten Headerdatei (je nachdem, ob ["/ Yu"](../build/reference/yu-use-precompiled-header-file.md) oder ["/ Yc"](../build/reference/yc-create-precompiled-header-file.md) angegeben ist). Wenn *Filename* enthält keine Pfadangabe wird angenommen, dass die vorkompilierte Headerdatei im selben Verzeichnis wie die Quelldatei werden.  
  
 Wenn eine C- oder C++-Datei enthält eine **Hdrstop** Pragma, wenn mit/Yc kompiliert, der Compiler speichert den Zustand der Kompilierung bis zur Position des Pragmas. Der kompilierte Zustand von Code, der dem Pragma folgt, wird nicht gespeichert.  
  
 Verwendung *Filename* um die vorkompilierte Headerdatei zu benennen, in der der kompilierte Zustand gespeichert wird. Ein Leerzeichen zwischen **Hdrstop** und *Filename* ist optional. Der Dateiname angegeben wird, der **Hdrstop** Pragma ist eine Zeichenfolge und daher gelten die Beschränkungen, die eine beliebige Zeichenfolge C- oder C++. Insbesondere ist die Einschließung in Anführungszeichen und die Verwendung von Escapezeichen (umgekehrter Schrägstrich) erforderlich, um Verzeichnisnamen anzugeben. Zum Beispiel:  
  
```  
#pragma hdrstop( "c:\\projects\\include\\myinc.pch" )  
```  
  
 Der Name der vorkompilierten Headerdatei wird gemäß den folgenden Regeln, in Rangfolge aufgelistet, bestimmt:  
  
1.  Das Argument für die /Fp-Compileroption  
  
2.  Die *Filename* Argument #**Pragma Hdrstop**  
  
3.  Der Basisname der Quelldatei mit einer .PCH-Erweiterung  
  
 Für die Optionen "/ Yc" und "/ Yu", wenn keines der beiden Kompilierungsoptionen noch die **Hdrstop** Pragma gibt einen Dateinamen an, der Basisname der Quelldatei als den Basisnamen für die vorkompilierte Headerdatei verwendet.  
  
 Sie können auch Präprozessorbefehle wie folgt verwenden, um Makroersetzung auszuführen:  
  
```  
#define INCLUDE_PATH "c:\\progra~`1\\devstsu~1\\vc\\include\\"  
#define PCH_FNAME "PROG.PCH"  
.  
.  
.  
#pragma hdrstop( INCLUDE_PATH PCH_FNAME )  
```  
  
 Die folgenden Regeln bestimmen, wo die **Hdrstop** Pragma platziert werden kann:  
  
-   Es muss außerhalb einer Daten- oder Funktionsdeklaration oder -definition angezeigt werden.  
  
-   Es muss in der Quelldatei, nicht in einer Headerdatei angegeben werden.  
  
## <a name="example"></a>Beispiel  
  
```  
#include <windows.h>                 // Include several files  
#include "myhdr.h"  
  
__inline Disp( char *szToDisplay )   // Define an inline function  
{  
    ...                              // Some code to display string  
}  
#pragma hdrstop  
```  
  
 In diesem Beispiel wird die **Hdrstop** Pragma angezeigt wird, nachdem zwei Dateien einbezogen wurden und eine Inlinefunktion definiert wurde. Dies erscheint auf den ersten Blick eher als eine ungewöhnliche Platzierung für das Pragma. Beachten Sie jedoch, dass beim Verwenden der manuellen Vorkompilierungsoptionen, "/ Yc" und "/ Yu", mit der **Hdrstop** Pragma ermöglicht Ihnen die ganze Quelldateien Vorkompilieren – sogar Inlinecode. Mit dem Microsoft-Compiler können nicht nur Datendeklarationen vorkompiliert werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)