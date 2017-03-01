---
title: _CrtDbgBreak | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtDbgBreak
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
- _CrtDbgBreak
- CrtDbgBreak
dev_langs:
- C++
helpviewer_keywords:
- CrtDbgBreak function
- _CrtDbgBreak function
ms.assetid: 01f8b4a2-a2c7-4e1f-9f39-e573b4a7871f
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 105b86a3c06c17bd9d24ff6cedb213abf06dadcd
ms.lasthandoff: 02/24/2017

---
# <a name="crtdbgbreak"></a>_CrtDbgBreak
Legt einen Haltepunkt in einer bestimmten Zeile des Codes (Nur im Debugmodus aktiviert)  
  
## <a name="syntax"></a>Syntax  
  
```  
void _CrtDbgBreak( void );  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Es ist kein Rückgabewert vorhanden.  
  
## <a name="remarks"></a>Hinweise  
 Die `_CrtDbgBreak`-Funktion legt einen Debughaltepunkt auf eine bestimmte Codezeile fest, in der sich die Funktion befindet. Diese Funktion wird nur im Debugmodus verwendet und ist abhängig von `_DEBUG`, was zuvor definiert wurde.  
  
 Weitere Informationen zur Verwendung anderer hookfähiger Laufzeitfunktionen und zum Schreiben eigener clientdefinierter Hookfunktionen finden Sie unter [Writing Your Own Debug Hook Functions (Schreiben von Hookfunktionen zum Debuggen)](/visualstudio/debugger/debug-hook-function-writing).  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_CrtDbgBreak`|\<CRTDBG.h>|  
  
## <a name="libraries"></a>Bibliotheken  
 Nur Debugversionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)   
 [__debugbreak](../../intrinsics/debugbreak.md)
