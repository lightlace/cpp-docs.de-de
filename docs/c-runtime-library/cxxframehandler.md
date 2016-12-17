---
title: "__CxxFrameHandler"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "__CxxFrameHandler"
apilocation: 
  - "msvcr110.dll"
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__CxxFrameHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__CxxFrameHandler"
ms.assetid: b79ac97f-425a-42ae-9b91-8beaef935333
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "corob"
manager: "ghogen"
---
# __CxxFrameHandler
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Interne CRT\-Funktion.  Wird von CRT verwendet, um Frames für strukturierte Ausnahmen zu verarbeiten.  
  
## Syntax  
  
```cpp  
EXCEPTION_DISPOSITION __CxxFrameHandler(       EHExceptionRecord  *pExcept,       EHRegistrationNode *pRN,       void               *pContext,        DispatcherContext  *pDC    )  
```  
  
#### Parameter  
 `pExcept`  
 Ausnahmeaufzeichnung, die an die möglichen `catch`\-Anweisungen übergeben wird.  
  
 `pRN`  
 Dynamische Informationen über den Stapelrahmen, der zur Verarbeitung der Ausnahme verwendet wird.  Weitere Informationen finden Sie unter ehdata.h.  
  
 `pContext`  
 Kontext.  \(Wird bei Intel\-Prozessoren nicht verwendet.\)  
  
 `pDC`  
 Zusätzliche Informationen über den Funktionsstart und den Stapelrahmen.  
  
## Rückgabewert  
 Einer der *Filterausdruckswerte*, die vom [try\-except\-Anweisung](../cpp/try-except-statement.md) verwendet werden.  
  
## Hinweise  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|\_\_CxxFrameHandler|excpt.h, ehdata.h|