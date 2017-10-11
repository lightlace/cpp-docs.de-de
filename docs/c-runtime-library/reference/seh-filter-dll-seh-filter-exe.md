---
title: _seh_filter_dll, _seh_filter_exe | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _XcptFilter
- _seh_filter_dll
- _seh_filter_exe
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- XcptFilter
- _XcptFilter
- _seh_filter_dll
- _seh_filter_exe
- corecrt_startup/_seh_filter_exe
- corecrt_startup/_seh_filter_dll
dev_langs:
- C++
helpviewer_keywords:
- XcptFilter function
- _XcptFilter function
- _seh_filter_dll function
- _seh_filter_exe function
ms.assetid: 747e5963-3a12-4bf5-b5c4-d4c1b6068e15
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 677e203e552dfa2f057cb0631d73c9f48349c4b4
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="sehfilterdll-sehfilterexe"></a>_seh_filter_dll, _seh_filter_exe
Gibt die Ausnahme und die zugehörige Aktion an, die ausgeführt werden soll.  
  
## <a name="syntax"></a>Syntax  
  
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
  
#### <a name="parameters"></a>Parameter  
 [in] `_ExceptionNum`  
 Der Bezeichner für die Ausnahme.  
  
 [in] `_ExceptionPtr`  
 Ein Zeiger auf die Ausnahmeinformationen.  
  
## <a name="return-value"></a>Rückgabewert  
 Eine ganze Zahl, die entsprechend dem Ergebnis der Ausnahmeverarbeitung die Aktion angibt, die ausgeführt werden soll.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methoden werden durch den Ausnahmefilterausdruck [try-except-Anweisung](../../cpp/try-except-statement.md) aufgerufen. Die Methode fragt eine interne Tabelle mit Konstanten ab, um die Ausnahme zu ermitteln und die geeignete Aktion zu bestimmen (siehe nächste Tabelle). Die Ausnahmenummern sind in „winnt.h“ definiert, und die Signalnummern sind in „signal.h“ definiert.  
  
|Ausnahmenummer (unsigned long)|Signalnummer|  
|----------------------------------------|-------------------|  
|STATUS_ACCESS_VIOLATION|SIGSEGV|  
|STATUS_ILLEGAL_INSTRUCTION|SIGILL|  
|STATUS_PRIVILEGED_INSTRUCTION|SIGILL|  
|STATUS_FLOAT_DENORMAL_OPERAND|SIGFPE|  
|STATUS_FLOAT_DIVIDE_BY_ZERO|SIGFPE|  
|STATUS_FLOAT_INEXACT_RESULT|SIGFPE|  
|STATUS_FLOAT_INVALID_OPERATION|SIGFPE|  
|STATUS_FLOAT_OVERFLOW|SIGFPE|  
|STATUS_FLOAT_STACK_CHECK|SIGFPE|  
|STATUS_FLOAT_UNDERFLOW|SIGFPE|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corecrt_startup.h  
  
## <a name="see-also"></a>Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)
