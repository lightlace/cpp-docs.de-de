---
title: _set_abort_behavior | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _set_abort_behavior
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
- _set_abort_behavior
- set_abort_behavior
dev_langs:
- C++
helpviewer_keywords:
- aborting programs
- _set_abort_behavior function
- set_abort_behavior function
ms.assetid: 43918766-e4ba-4b1f-80e8-1a4a910cd452
caps.latest.revision: 26
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: edf31ccddfb9ab2eaa6de226ff4ec7eb09869438
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="setabortbehavior"></a>_set_abort_behavior
Gibt die Aktion an, die ausgeführt werden soll, wenn ein Programm nicht normal beendet wird.  
  
> [!NOTE]
>  Verwenden Sie nicht die `abort`-Funktion, um eine [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]-App zu schließen, außer bei Tests oder in Debugszenarios. Programmgesteuerte oder UI-Methoden zum Schließen einer [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]-App sind gemäß den [Zertifizierungsanforderungen für Windows 8-Apps](http://go.microsoft.com/fwlink/?LinkId=262889) nicht zulässig. Weitere Informationen finden Sie unter [Anwendungslebenszyklus (Windows Store-Apps)](http://go.microsoft.com/fwlink/?LinkId=262853).  
  
## <a name="syntax"></a>Syntax  
  
```  
unsigned int _set_abort_behavior(  
   unsigned int flags,  
   unsigned int mask  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `flags`  
 Neuer Wert der `abort`-Flags.  
  
 [in] `mask`  
 Maske für die festzulegenden Bits der `abort`-Flags.  
  
## <a name="return-value"></a>Rückgabewert  
 Der alte Wert der Flags.  
  
## <a name="remarks"></a>Hinweise  
 Es gibt zwei `abort`-Flags: `_WRITE_ABORT_MSG` und `_CALL_REPORTFAULT`. `_WRITE_ABORT_MSG` bestimmt, ob eine informative Textmeldung gedruckt werden soll, wenn ein Programm nicht normal beendet wird. Die Meldung sagt aus, dass die Anwendung die `abort`-Funktion aufgerufen hat. Beim Standardverhalten wird die Meldung ausgeben. Wenn `_CALL_REPORTFAULT`festgelegt ist, wird ein Watson-Absturzabbild generiert und beim Aufruf von `abort` ausgegeben. Standardmäßig ist die Absturzabbildberichterstellung in den Nichtdebugversionen aktiviert.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_set_abort_behavior`|\<stdlib.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
  
```C  
// crt_set_abort_behavior.c  
// compile with: /TC  
#include <stdlib.h>  
  
int main()  
{  
   printf("Suppressing the abort message. If successful, this message"  
          " will be the only output.\n");  
   // Suppress the abort message  
   _set_abort_behavior( 0, _WRITE_ABORT_MSG);  
   abort();  
}  
```  
  
```Output  
Suppressing the abort message. If successful, this message will be the only output.  
```  
  
## <a name="see-also"></a>Siehe auch  
 [abort](../../c-runtime-library/reference/abort.md)
