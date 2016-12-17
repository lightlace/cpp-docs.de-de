---
title: "_CxxThrowException"
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
  - "_CxxThrowException"
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
  - "CxxThrowException"
  - "_CxxThrowException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CxxThrowException-Funktion"
  - "CxxThrowException-Funktion"
ms.assetid: 0b90bef5-b7d2-46e0-88e2-59e531e01a4d
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# _CxxThrowException
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erstellt den Ausnahmedatensatz und die Laufzeitumgebung auf, um der Verarbeitung der Ausnahme zu beginnen.  
  
## Syntax  
  
```  
extern "C" void __stdcall _CxxThrowException(  
   void* pExceptionObject  
   _ThrowInfo* pThrowInfo  
);  
```  
  
#### Parameter  
 \[in\] `pExceptionObject`  
 Das Objekt, das die Ausnahme generiert hat.  
  
 \[in\] `pThrowInfo`  
 Die Informationen, die erforderlich ist, die Ausnahme zu verarbeiten.  
  
## Hinweise  
 Diese Methode wird in einer nur für Compiler Datei enthalten, die der Compiler verwendet, um Ausnahmen zu verarbeiten.  Rufen Sie die Methode nicht direkt vom Code aufzurufen.  
  
## Anforderungen  
 **Quelle:** Throw.cpp  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)