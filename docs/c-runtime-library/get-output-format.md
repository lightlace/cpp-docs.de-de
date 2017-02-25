---
title: "_get_output_format | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_output_format"
apilocation: 
  - "msvcr110_clr0400.dll"
  - "msvcr100.dll"
  - "msvcr80.dll"
  - "msvcrt.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
  - "msvcr110.dll"
apitype: "DLLExport"
f1_keywords: 
  - "get_output_format"
  - "_get_output_format"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_get_output_format-Funktion"
  - "get_output_format-Funktion"
  - "Ausgabeformatierung"
ms.assetid: 0ce42f3b-3479-41c4-bcbf-1d21f7ee37e7
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# _get_output_format
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ruft den aktuellen Wert des Ausgabeformatkennzeichens ab.  
  
> [!IMPORTANT]
>  Diese Funktion ist veraltet. Von Visual Studio 2015 an ist sie nicht in der CRT verfügbar.  
  
## Syntax  
  
```  
unsigned int _get_output_format();  
```  
  
## Rückgabewert  
 Der aktuelle Wert des Ausgabeformatkennzeichens.  
  
## Hinweise  
 Das Ausgabeformatkennzeichen steuert Funktionen von formatierter E\/A. Derzeit hat das Kennzeichen zwei mögliche Werte: 0 und `_TWO_DIGIT_EXPONENT`. Wenn `_TWO_DIGIT_EXPONENT` festgelegt ist, werden Gleitkommazahlen mit nur zwei Stellen im Exponenten gedruckt, es sei denn, eine dritte Stelle ist aufgrund der Größe des Exponenten erforderlich. Wenn das Kennzeichen den Wert 0 hat, wird in der Gleitkommadarstellung ein dreistelliger Exponent angezeigt, der ggf. mit Nullen aufgefüllt wird.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_get_output_format`|\<stdio.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../c-runtime-library/compatibility.md) in der Einführung.  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [printf\_s, \_printf\_s\_l, wprintf\_s, \_wprintf\_s\_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)   
 [printf\-Typenfeldzeichen](../c-runtime-library/printf-type-field-characters.md)   
 [\_set\_output\_format](../c-runtime-library/set-output-format.md)