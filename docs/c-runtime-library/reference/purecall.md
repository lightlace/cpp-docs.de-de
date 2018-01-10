---
title: _purecall | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _purecall
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
- ntoskrnl.exe
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- purecall
- _purecall
dev_langs: C++
helpviewer_keywords:
- _purecall function
- purecall function
ms.assetid: 56135d9b-3403-4e22-822d-e714523801cc
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8ef2670188374dc7af5fa34c76df73c3d261efc4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="purecall"></a>_purecall
Der standardmäßige rein virtuelle Fehlerhandler für Funktionsaufrufe. Der Compiler generiert Code zum Aufrufen dieser Funktion, wenn eine rein virtuelle Memberfunktion aufgerufen wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
extern "C" int __cdecl _purecall();  
```  
  
## <a name="remarks"></a>Hinweise  
 Die `_purecall`-Funktion ist ein Microsoft-spezifisches Implementierungsdetail des Microsoft Visual C++-Compilers. Diese Funktion soll nicht direkt von Ihrem Code aufgerufen werden, und sie hat keine öffentliche Header-Deklaration. Es ist hier dokumentiert, da es sich um einen öffentlichen Export der C-Laufzeitbibliothek handelt.  
  
 Ein Aufruf an eine rein virtuelle Funktion ist ein Fehler, da sie keine Implementierung hat. Der Compiler generiert Code zum Aufrufen der `_purecall`-Fehlerhandlerfunktion, wenn eine rein virtuelle Funktion aufgerufen wird. In der Standardeinstellung wird das Programm von `_purecall` beendet. Vor dem Beenden ruft die `_purecall`-Funktion eine `_purecall_handler`-Funktion auf, wenn eine für den Prozess festgelegt wurde. Sie können Ihre eigene Fehlerhandlerfunktion für rein virtuelle Funktionsaufrufe installieren, um sie für das Debuggen und für Berichtszwecke abzufangen. Um Ihren eigenen Fehlerhandler zu verwenden, erstellen Sie eine Funktion mit der `_purecall_handler`-Signatur und verwenden Sie anschließend [_set_purecall_handler](../../c-runtime-library/reference/get-purecall-handler-set-purecall-handler.md), um ihn als den aktuellen Handler festzulegen.  
  
## <a name="requirements"></a>Anforderungen  
 Die `_purecall`-Funktion verfügt nicht über eine Header-Deklaration. Die `_purecall_handler`-Typedefinition ist in \<stdlib.h > definiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Alphabetical Function Reference (Alphabetische Funktionsreferenz)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [_get_purecall_handler, _set_purecall_handler](../../c-runtime-library/reference/get-purecall-handler-set-purecall-handler.md)