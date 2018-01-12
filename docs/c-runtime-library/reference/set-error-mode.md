---
title: _set_error_mode | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _set_error_mode
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
- set_error_mode
- _set_error_mode
dev_langs: C++
helpviewer_keywords:
- _set_error_mode function
- set_error_mode function
ms.assetid: f0807be5-73d1-4a32-a701-3c9bdd139c5c
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7987686fb0b9faa03cf4d5e4795116e9f0a608bd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="seterrormode"></a>_set_error_mode
Ändert `__error_mode`, um einen nicht standardmäßigen Speicherort zu bestimmen, an dem die C-Laufzeit eine Fehlermeldung für einen Fehler schreibt, der das Programm beenden kann.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [In /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntax  
  
```  
int _set_error_mode(  
   int modeval   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `modeval`  
 Ziel der Fehlermeldungen.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt die alte Einstellung oder -1 zurück, wenn ein Fehler auftritt.  
  
## <a name="remarks"></a>Hinweise  
 Steuert die Fehlerausgabesenke durch Festlegen des Werts von `__error_mode`. Sie können z. B. die Ausgabe in einen Standardfehler umleiten oder die `MessageBox`-API verwenden.  
  
 Der Parameter `modeval` kann auf einen der folgenden Werte festgelegt werden:  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`_OUT_TO_DEFAULT`|Fehlersenke wird durch `__app_type` bestimmt.|  
|`_OUT_TO_STDERR`|Fehlersenke ist ein Standardfehler.|  
|`_OUT_TO_MSGBOX`|Fehlersenke ist ein Meldungsfeld.|  
|`_REPORT_ERRMODE`|Melden Sie den aktuellen `__error_mode`-Wert.|  
  
 Wenn ein anderer Wert als die aufgeführten übergeben wird, wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, setzt `_set_error_mode` `errno` auf `EINVAL` und gibt -1 zurück.  
  
 Bei Verwendung mit [assert](../../c-runtime-library/reference/assert-macro-assert-wassert.md) zeigt `_set_error_mode` die fehlerhafte Anweisung im Dialogfeld an und bietet Ihnen die Möglichkeit, die Schaltfläche `Ignore` auszuwählen, sodass Sie das Programm weiter ausführen können.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_set_error_mode`|\<stdlib.h>|  
  
## <a name="example"></a>Beispiel  
  
```C  
// crt_set_error_mode.c  
// compile with: /c  
#include <stdlib.h>  
#include <assert.h>  
  
int main()  
{  
   _set_error_mode(_OUT_TO_STDERR);  
   assert(2+2==5);  
}  
```  
  
```Output  
Assertion failed: 2+2==5, file crt_set_error_mode.c, line 8  
  
This application has requested the Runtime to terminate it in an unusual way.  
Please contact the application's support team for more information.  
```  
  
## <a name="see-also"></a>Siehe auch  
 [assert Macro, _assert, _wassert](../../c-runtime-library/reference/assert-macro-assert-wassert.md)