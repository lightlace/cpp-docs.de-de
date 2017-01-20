---
title: "_CrtDbgBreak"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_CrtDbgBreak"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_CrtDbgBreak"
  - "CrtDbgBreak"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_CrtDbgBreak-Funktion"
  - "CrtDbgBreak-Funktion"
ms.assetid: 01f8b4a2-a2c7-4e1f-9f39-e573b4a7871f
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# _CrtDbgBreak
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt einen Haltepunkt an einer bestimmten Codezeile fest. \(Wird nur im Debugmodus.\)  
  
## Syntax  
  
```  
void _CrtDbgBreak( void );  
```  
  
## Rückgabewert  
 Es gibt keinen Rückgabewert.  
  
## Hinweise  
 Die `_CrtDbgBreak`\-Funktion legt einen debuggenshaltepunkt auf der bestimmten Codezeile fest, wo sich die Funktion befindet.  Diese Funktion wird nur im Debugmodus verwendet und ist von `_DEBUG` abhängig, das zuvor definiert wird.  
  
 Weitere Informationen über die Verwendung anderer Hook\-fähiger Laufzeitfunktionen und das Schreiben eigener clientdefinierten Hookfunktionen, finden Sie unter [eigene Schreiben, debuggen Sie Hookfunktionen](../Topic/Debug%20Hook%20Function%20Writing.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_CrtDbgBreak`|\<CRTDBG.h\>|  
  
## Bibliotheken  
 Nur Debugversionen von [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)   
 [\_\_debugbreak](../../intrinsics/debugbreak.md)