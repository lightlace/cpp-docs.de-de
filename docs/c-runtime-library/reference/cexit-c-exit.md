---
title: _cexit, _c_exit | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _c_exit
- _cexit
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
- _cexit
- c_exit
- _c_exit
- cexit
dev_langs:
- C++
helpviewer_keywords:
- cleanup operations during processes
- cexit function
- _c_exit function
- _cexit function
- c_exit function
ms.assetid: f3072045-9924-4b1a-9fef-b0dcd6d12663
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: a68b803ee7dc444439d7a62f43cf7157e7fbf505
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="cexit-cexit"></a>_cexit, _c_exit
Führt Bereinigungsvorgänge aus und kehrt zurück, ohne dass der Prozess beendet wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
void _cexit( void );  
void _c_exit( void );  
```  
  
## <a name="remarks"></a>Hinweise  
 Die `_cexit`-Funktion ruft die von `atexit` und `_onexit` registrierten Funktionen in der Reihenfolge LIFO (Last In, First Out) auf. Dann leert `_cexit` alle E/A-Puffer und schließt vor der Rückkehr alle geöffneten Streams. `_c_exit` entspricht `_exit`, kehrt jedoch zum aufrufenden Prozess zurück, ohne `atexit` oder `_onexit` zu verarbeiten oder Streampuffer zu leeren. Der Verhalten von `exit`,`_exit`,`_cexit` und `_c_exit` wird in der folgenden Tabelle gezeigt.  
  
|Funktion|Verhalten|  
|--------------|--------------|  
|`exit`|Führt vollständige C-Bibliotheksbeendigungsprozeduren aus, beendet den Prozess und beendet mit dem angegebenen Statuscode.|  
|`_exit`|Führt schnelle C-Bibliotheksbeendigungsprozeduren aus, beendet den Prozess und beendet mit dem angegebenen Statuscode.|  
|`_cexit`|Führt vollständige C-Bibliotheksbeendigungsprozeduren aus und kehrt zum Aufrufer zurück, beendet jedoch nicht den Prozess.|  
|`_c_exit`|Führt schnelle C-Bibliotheksbeendigungsprozeduren aus und kehrt zum Aufrufer zurück, beendet jedoch nicht den Prozess.|  
  
 Beim Aufruf der Funktionen `_cexit` oder `_c_exit` werden die Destruktoren für jedes zum Zeitpunkt des Aufrufs vorhandene temporäre oder automatische Objekt nicht aufgerufen. Ein automatisches Objekt ist ein Objekt, das in einer Funktion definiert wird, in der das Objekt nicht als statisch deklariert ist. Ein temporäres Objekt ist ein Objekt, das vom Compiler erstellt wird. Zum Zerstören eines automatischen Objekts müssen Sie vor dem Aufrufen von `_cexit` oder `_c_exit` den Destruktor für das Objekt explizit wie folgt aufrufen:  
  
```  
myObject.myClass::~myClass( );  
```  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_cexit`|\<process.h>|  
|`_c_exit`|\<process.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="see-also"></a>Siehe auch  
 [Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [_exec- und _wexec-Funktionen](../../c-runtime-library/exec-wexec-functions.md)   
 [exit, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [_onexit, _onexit_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [_spawn, _wspawn-Funktionen](../../c-runtime-library/spawn-wspawn-functions.md)   
 [system, _wsystem](../../c-runtime-library/reference/system-wsystem.md)
