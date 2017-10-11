---
title: __security_init_cookie | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- __security_init_cookie
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
- security_init_cookie
- __security_init_cookie
dev_langs:
- C++
helpviewer_keywords:
- security cookie [C++]
- __security_init_cookie function
- security_init_cookie function
- global security cookie
ms.assetid: 32119905-0897-4a1c-84ca-bffd16c9b2af
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 249fc38a36ee0f3a61b6347b48219154bada7d22
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="securityinitcookie"></a>__security_init_cookie
Initialisiert das globale Sicherheitscookie.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __security_init_cookie(void);  
```  
  
## <a name="remarks"></a>Hinweise  
 Das globale Sicherheitscookie wird zum Schutz vor Pufferüberlauf in dem Code verwendet, der mit [/GS (Puffer-Sicherheitsüberprüfung)](../../build/reference/gs-buffer-security-check.md) kompiliert wurde, sowie in Code mit Ausnahmebehandlung. Beim Einstieg in eine vor Pufferüberlauf geschützte Funktion wird das Cookie auf dem Stapel abgelegt, und bei Funktionsende wird der Wert auf dem Stapel mit dem globalen Cookie verglichen. Jeglicher Unterschied zwischen diesen Werten weist darauf hin, dass ein Pufferüberlauf eingetreten ist. Das Programm wird daraufhin sofort beendet.  
  
 Normalerweise wird `__security_init_cookie` von der C-Laufzeitbibliothek (CRT) beim Start aufgerufen. Wenn Sie die CRT-Initialisierung umgehen, z.B. wenn Sie [/ENTRY](../../build/reference/entry-entry-point-symbol.md) zum Angeben eines Einstiegspunkts verwenden, müssen Sie `__security_init_cookie` selbst aufrufen. Wenn `__security_init_cookie` nicht aufgerufen wird, wird das globale Sicherheitscookie auf den Standardwert festgelegt, und der Schutz vor Pufferüberlauf ist beeinträchtigt. Da ein Angreifer diesen Cookie-Standardwert zum Manipulieren der Pufferüberlaufprüfungen nutzen kann, wird empfohlen, dass Sie beim Definieren Ihres eigenen Einstiegspunkts stets `__security_init_cookie` aufrufen.  
  
 Der Aufruf von `__security_init_cookie` muss erfolgen, bevor eine vor Pufferüberlauf geschützte Funktion eingegeben wird. Andernfalls wird ein unechter Pufferüberlauf erkannt. Weitere Informationen finden Sie unter [C-Laufzeitfehler R6035](../../error-messages/tool-errors/c-runtime-error-r6035.md).  
  
## <a name="example"></a>Beispiel  
 Beispiele finden Sie unter [C-Laufzeitfehler R6035](../../error-messages/tool-errors/c-runtime-error-r6035.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`__security_init_cookie`|\<process.h>|  
  
 `__security_init_cookie` ist eine Microsoft-Erweiterung der Standard-C-Laufzeitbibliothek. Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Compiler-Sicherheitsprüfungen im Detail](http://go.microsoft.com/fwlink/?linkid=7260)
