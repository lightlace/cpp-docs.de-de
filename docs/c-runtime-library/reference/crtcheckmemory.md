---
title: _CrtCheckMemory | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtCheckMemory
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
apitype: DLLExport
f1_keywords:
- CrtCheckMemory
- _CrtCheckMemory
dev_langs:
- C++
helpviewer_keywords:
- _CrtCheckMemory function
- CrtCheckMemory function
ms.assetid: 457cc72e-60fd-4177-ab5c-6ae26a420765
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 82b64afbdd80e9b1433f8f9873b4e295fc2e20c1
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="crtcheckmemory"></a>_CrtCheckMemory
Bestätigt die Integrität der Speicherblöcke, die im Debugheap zugeordnet werden (nur Debugversion).  
  
## <a name="syntax"></a>Syntax  
  
```  
  
int _CrtCheckMemory( void );  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Bei Erfolg gibt `_CrtCheckMemory` den Wert TRUE zurück. Andernfalls gibt die Funktion FALSE zurück.  
  
## <a name="remarks"></a>Hinweise  
 Die `_CrtCheckMemory`-Funktion überprüft den vom Debugheapmanager belegten Speicher, indem der zugrunde liegende Basisheap überprüft und jeder Speicherblock untersucht wird. Wenn im zugrunde liegenden Basisheap, in den Debugheaderinformationen oder den Überschreibungspuffern Fehler oder Speicherinkonsistenzen auftreten, generiert `_CrtCheckMemory` einen Debugbericht mit Informationen, die die Fehlerbedingung beschreiben. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von `_CrtCheckMemory` während der Vorverarbeitung entfernt.  
  
 Das Verhalten von `_CrtCheckMemory` kann gesteuert werden, indem die Bitfelder des [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)-Flags mithilfe der [_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md)-Funktion festgelegt werden. Durch Aktivieren des**_CRTDBG_CHECK_ALWAYS_DF**-Bitfelds wird `_CrtCheckMemory` immer aufgerufen, wenn ein Speicherbelegungsvorgang angefordert wird. Obwohl diese Methode die Ausführung verlangsamt, ist sie nützlich, um Fehler schell zu erfassen. Durch Deaktivieren des **_CRTDBG_ALLOC_MEM_DF**-Bitfelds wird bewirkt, dass `_CrtCheckMemory` den Heap nicht überprüft und unverzüglich den Wert **TRUE** zurückgibt.  
  
 Da diese Funktion **TRUE** oder **FALSE** zurückgibt, kann sie an eine der [_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)-Makros übergeben werden, um einen einfachen Debug-Fehlerbehandlungsmechanismus zu erstellen. Im folgenden Beispiel wird ein Assertionsfehler ausgelöst, wenn eine Beschädigung im Heap erkannt wird:  
  
```  
_ASSERTE( _CrtCheckMemory( ) );  
```  
  
 Weitere Informationen dazu, wie `_CrtCheckMemory` mit anderen Debugfunktionen verwendet werden kann, finden Sie unter [Heap State Reporting Functions (Berichtsfunktionen für den Heapzustand)](/visualstudio/debugger/crt-debug-heap-details). Eine Übersicht der Speicherverwaltung und des Debugheaps finden Sie unter [Details zum CRT-Debugheap](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_CrtCheckMemory`|\<crtdbg.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="libraries"></a>Bibliotheken  
 Nur Debugversionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Beispiel  
 Ein Beispiel für die Verwendung von `_CrtCheckMemory` finden Sie unter [crt_dbg1](http://msdn.microsoft.com/en-us/17b4b20c-e849-48f5-8eb5-dca6509cbaf9).  
  
## <a name="see-also"></a>Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)   
 [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)   
 [_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md)
