---
title: "#line-Direktive (C/C++)"
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
  - "#line"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#line-Direktive"
  - "line-Direktive (#line)"
  - "Präprozessor, Direktiven"
ms.assetid: 585c1dc4-5184-4f01-98f4-80c1909744d7
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# #line-Direktive (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die `#line`\-Direktive weist den Präprozessor an, die vom Compiler intern gespeicherte Zeilennummer und den Dateinamen in eine bestimmte Zeilennummer und einen bestimmten Dateinamen zu ändern.  
  
## Syntax  
  
```  
  
#line   
digit-sequence ["filename"]  
```  
  
## Hinweise  
 Der Compiler verwendet die Zeilennummer und den optionalen Dateinamen, um auf Fehler zu verweisen, die während der Kompilierung gefunden werden.  Die Zeilennummer verweist normalerweise auf die aktuelle Eingabezeile, und der Dateiname verweist auf die aktuelle Eingabedatei.  Nach der Verarbeitung jeder Zeile wird die Zeilennummer erhöht.  
  
 Die Wert der *Ziffernfolge* kann eine beliebige Integerkonstante sein.  Makroersetzungen können für die Vorverarbeitungstoken durchgeführt werden, das Ergebnis muss jedoch anhand der richtigen Syntax ausgewertet werden.  *filename* kann eine beliebige Kombination von Zeichen sein und muss in doppelte Anführungszeichen gesetzt werden \(**" "**\).  Wenn *filename* ausgelassen wird, bleibt der vorherige Dateiname unverändert.  
  
 Sie können auch die Quellzeilennummer und den Quelldateinamen ändern, indem Sie eine `#line`\-Direktiven schreiben.  Das Konvertierungsprogramm verwendet die Zeilennummer und den Dateinamen, um die Werte der vordefinierten Makros **\_\_FILE\_\_** und **\_\_LINE\_\_** zu bestimmen.  Sie können diese Makros verwenden, um selbsterklärende Fehlermeldungen in den Programmtext einzufügen.  Weitere Informationen zu diesen vordefinierten Makros finden Sie unter [Vordefinierte Makros](../preprocessor/predefined-macros.md).  
  
 Das **\_\_FILE\_\_**\-Makro wird in eine Zeichenfolge erweitert, deren Inhalt der Dateiname in doppelten Anführungszeichen \(**" "**\) ist.  
  
 Wenn Sie die Zeilennummer und den Dateinamen ändern, ignoriert der Compiler die vorherigen Werte und setzt die Verarbeitung mit den neuen Werten fort.  Die `#line`\-Direktive wird in der Regel von Programm\-Generatoren verwendet, damit Fehlermeldungen auf die ursprüngliche Quelldatei und nicht auf das generierte Programm verweisen.  
  
 Die folgenden Beispiele veranschaulichen `#line` sowie die Makros **\_\_LINE\_\_** und **\_\_FILE\_\_**.  
  
 In dieser Anweisung wird die intern gespeicherte Zeilennummer auf 151 festgelegt, und der Dateiname wird in `copy.c` geändert.  
  
```  
#line 151 "copy.c"  
```  
  
 In diesem Beispiel verwendet das `ASSERT`\-Makro die vordefinierten Makros **\_\_LINE\_\_** und **\_\_FILE\_\_**, um eine Fehlermeldung zur Quelldatei auszugeben, wenn eine angegebene "assertion" nicht "true" ist.  
  
```  
#define ASSERT(cond)  
  
if( !(cond) )\  
{printf( "assertion error line %d, file(%s)\n", \  
__LINE__, __FILE__ );}  
```  
  
## Siehe auch  
 [Präprozessordirektiven](../preprocessor/preprocessor-directives.md)