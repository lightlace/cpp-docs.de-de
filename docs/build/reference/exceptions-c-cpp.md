---
title: Ausnahmen (C/C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- ERROR_MOD_NOT_FOUND
- vcppException
- ERROR_SEVERITY_ERROR
dev_langs:
- C++
helpviewer_keywords:
- vcppException
- C++ exception handling, delayed loading of DLLs
- delayed loading of DLLs, exceptions
- ERROR_SEVERITY_ERROR exception
- ERROR_MOD_NOT_FOUND exception
ms.assetid: c03be05d-1c39-4f35-84cf-00c9af3bae9a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 40a3a9e1cf1384603d6b7d95fa5960e951f932ef
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43216882"
---
# <a name="exceptions-cc"></a>Ausnahmen (C/C++)
Zwei Ausnahmecodes können ausgelöst werden, wenn Fehler auftreten:  
  
-   Für eine **LoadLibrary** Fehler  
  
-   Für eine **GetProcAddress** Fehler  
  
 Hier sind die Ausnahmeinformationen:  
  
```  
//  
// Exception information  
//  
#define FACILITY_VISUALCPP  ((LONG)0x6d)  
#define VcppException(sev,err)  ((sev) | (FACILITY_VISUALCPP<<16) | err)  
```  
  
 Ausgelösten Ausnahmecodes sind die Standardwerte VcppException (ERROR_SEVERITY_ERROR, ERROR_MOD_NOT_FOUND) und die VcppException (ERROR_SEVERITY_ERROR, ERROR_PROC_NOT_FOUND)-Werte. Die Ausnahme übergibt einen Zeiger auf eine **DelayLoadInfo** Struktur in der LPDWORD-Wert, der abgerufen werden kann **GetExceptionInformation** in die [EXCEPTION_RECORD](/windows/desktop/api/winnt/ns-winnt-_exception_record) -Struktur, ExceptionInformation [0]-Feld.  
  
 Wenn die falschen Bits im Feld GrAttrs festgelegt sind, wird die Ausnahme darüber hinaus zusätzlich ausgelöst. Diese Ausnahme ist für praktisch, schwerwiegender.  
  
 Finden Sie unter [Struktur- und Konstantendefinitionen](../../build/reference/structure-and-constant-definitions.md) für Weitere Informationen.  
  
## <a name="see-also"></a>Siehe auch  
 [Fehlerbehandlung und Benachrichtigung](../../build/reference/error-handling-and-notification.md)