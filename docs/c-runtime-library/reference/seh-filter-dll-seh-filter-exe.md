---
title: "_seh_filter_dll, _seh_filter_exe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_XcptFilter"
  - "_seh_filter_dll"
  - "_seh_filter_exe"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "XcptFilter"
  - "_XcptFilter"
  - "_seh_filter_dll"
  - "_seh_filter_exe"
  - "corecrt_startup/_seh_filter_exe"
  - "corecrt_startup/_seh_filter_dll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "XcptFilter-Funktion"
  - "_XcptFilter-Funktion"
  - "_seh_filter_dll-Funktion"
  - "_seh_filter_exe-Funktion"
ms.assetid: 747e5963-3a12-4bf5-b5c4-d4c1b6068e15
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# _seh_filter_dll, _seh_filter_exe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt die Ausnahme und die zugehörige Aktion an, die ausgeführt werden soll.  
  
## Syntax  
  
```  
int __cdecl _seh_filter_dll(  
   unsigned long _ExceptionNum,  
   struct _EXCEPTION_POINTERS* _ExceptionPtr  
);  
int __cdecl _seh_filter_exe(  
   unsigned long _ExceptionNum,  
   struct _EXCEPTION_POINTERS* _ExceptionPtr  
);  
```  
  
#### Parameter  
 \[in\] `_ExceptionNum`  
 Der Bezeichner für die Ausnahme.  
  
 \[in\] `_ExceptionPtr`  
 Ein Zeiger auf die Ausnahmeinformationen.  
  
## Rückgabewert  
 Eine ganze Zahl, die entsprechend dem Ergebnis der Ausnahmeverarbeitung die Aktion angibt, die ausgeführt werden soll.  
  
## Hinweise  
 Diese Methoden werden durch den Ausnahmefilterausdruck der [try\-except\-Anweisung](../../cpp/try-except-statement.md) aufgerufen. Die Methode fragt eine interne Tabelle mit Konstanten ab, um die Ausnahme zu ermitteln und die geeignete Aktion zu bestimmen \(siehe nächste Tabelle\). Die Ausnahmenummern sind in „winnt.h“ definiert, und die Signalnummern sind in „signal.h“ definiert.  
  
|Ausnahmenummer \(unsigned long\)|Signalnummer|  
|--------------------------------------|------------------|  
|STATUS\_ACCESS\_VIOLATION|SIGSEGV|  
|STATUS\_ILLEGAL\_INSTRUCTION|SIGILL|  
|STATUS\_PRIVILEGED\_INSTRUCTION|SIGILL|  
|STATUS\_FLOAT\_DENORMAL\_OPERAND|SIGFPE|  
|STATUS\_FLOAT\_DIVIDE\_BY\_ZERO|SIGFPE|  
|STATUS\_FLOAT\_INEXACT\_RESULT|SIGFPE|  
|STATUS\_FLOAT\_INVALID\_OPERATION|SIGFPE|  
|STATUS\_FLOAT\_OVERFLOW|SIGFPE|  
|STATUS\_FLOAT\_STACK\_CHECK|SIGFPE|  
|STATUS\_FLOAT\_UNDERFLOW|SIGFPE|  
  
## Anforderungen  
 **Header:** corecrt\_startup.h  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)