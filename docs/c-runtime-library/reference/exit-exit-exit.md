---
title: exit, _Exit, _exit | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _exit
- exit
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
- Exit
- _exit
- process/exit
- process/_Exit
- stdlib/exit
- stdlib/_Exit
dev_langs:
- C++
helpviewer_keywords:
- exit function
- _exit function
- processes, terminating
- function calls, terminating
- process termination, calling
ms.assetid: b1501fa6-27c2-478c-9e93-cc4fd802a01f
caps.latest.revision: 17
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
ms.openlocfilehash: 8d6f75bb19c2cfd89d8714ed87ff91ddf340055e
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="exit-exit-exit"></a>exit, _Exit, _exit
Beendet den aufrufenden Prozess. Die Funktion `exit` beendet ihn nach der Bereinigung; `_exit` und `_Exit` beenden ihn sofort.  
  
> [!NOTE]
>  Verwenden Sie diese Methode nicht zum Herunterfahren einer UWP-App (Universal Windows Platform) oder einer [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] -App, mit Ausnahme von Test- oder Debugszenarien. Programmgesteuerte oder über die Benutzeroberfläche eingeleitete Verfahren zum Beenden einer [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] -App sind unzulässig. Weitere Informationen zu Windows 8- und 8.1-Apps finden Sie unter [App-Lebenszyklus](http://go.microsoft.com/fwlink/?LinkId=262853). Weitere Informationen zu Windows 10-Apps finden Sie unter [Anleitungen für Windows 10-Apps](http://go.microsoft.com/fwlink/p/?linkid=619133).  
  
## <a name="syntax"></a>Syntax  
  
```  
void exit(   
   int const status   
);  
void _Exit(   
   int const status   
);  
void _exit(   
   int const status   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `status`  
 Beendigungsstatuscode.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktionen `exit`, `_Exit` und `_exit` beenden den aufrufenden Prozess. Die Funktion `exit` ruft Destruktoren für threadlokale Objekte und anschließend – in LIFO-Reihenfolge (Last In First Out) – die Funktionen auf, die von `atexit` und `_onexit`registriert wurden; schließlich werden alle Puffer geleert, bevor der Prozess beendet wird. Die Funktionen `_Exit` und `_exit` beenden den Prozess, ohne threadlokale Objekte zu zerstören oder die Funktionen `atexit` oder `_onexit` zu verarbeiten, und ohne die Datenstrompuffer zu leeren.  
  
 Obwohl die Aufrufe `exit`, `_Exit` und `_exit` keinen Wert zurückgeben, wird das niedrige Byte von `status` der Hostumgebung oder dem ggf. wartenden aufrufenden Prozess zur Verfügung gestellt, nachdem der aufrufende Prozess beendet ist. Der Aufrufer legt den Wert von `status` normalerweise zur Kennzeichnen einer normalen Beendigung auf „0“ fest, auf einen anderen Wert, um einen Fehler anzugeben. Der `status` -Wert steht dem Betriebssystem-Batchbefehl `ERRORLEVEL` zur Verfügung und wird durch eine der beiden Konstanten repräsentiert: `EXIT_SUCCESS`, die einen Wert von 0 darstellt, oder `EXIT_FAILURE`, die einen Wert von 1 darstellt.  
  
 Die Funktionen `exit`, `_Exit`, `_exit`, `quick_exit`, `_cexit`und `_c_exit` verhalten sich wie folgt.  
  
|Funktion|Beschreibung|  
|--------------|-----------------|  
|`exit`|Führt vollständige C-Bibliotheksbeendigungsprozeduren aus, beendet den Prozess und übergibt den angegebenen Statuscode der Hostumgebung.|  
|`_Exit`|Führt minimale C-Bibliotheksbeendigungsprozeduren aus, beendet den Prozess und übergibt den angegebenen Statuscode der Hostumgebung.|  
|`_exit`|Führt minimale C-Bibliotheksbeendigungsprozeduren aus, beendet den Prozess und übergibt den angegebenen Statuscode der Hostumgebung.|  
|`quick_exit`|Führt schnelle C-Bibliotheksbeendigungsprozeduren aus, beendet den Prozess und übergibt den angegebenen Statuscode der Hostumgebung.|  
|`_cexit`|Führt vollständige C-Bibliotheksbeendigungsprozeduren aus und kehrt zum Aufrufer zurück. Der Prozess wird nicht beendet.|  
|`_c_exit`|Führt minimale C-Bibliotheksbeendigungsprozeduren aus und kehrt zum Aufrufer zurück. Der Prozess wird nicht beendet.|  
  
 Beim Aufruf der Funktion `exit`,  `_Exit` oder `_exit` werden die Destruktoren für jedes zum Zeitpunkt des Aufrufs vorhandene temporäre oder automatische Objekt nicht aufgerufen. Ein automatisches Objekt wird in einer Funktion definiert, in der das Objekt nicht als statisch deklariert ist. Ein temporäres Objekt ist ein Objekt, das vom Compiler erstellt wird. Zum Zerstören eines automatischen Objekts müssen Sie vor dem Aufrufen von `exit`, `_Exit`oder `_exit`den Destruktor für das Objekt explizit wie folgt aufrufen:  
  
```  
myObject.myClass::~myClass();  
```  
  
 Verwenden Sie nicht `DLL_PROCESS_ATTACH` , um `exit` aus `DllMain`aufzurufen. Wenn Sie die `DLLMain` -Funktion beenden möchten, geben Sie `FALSE` von `DLL_PROCESS_ATTACH`zurück.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------|  
|`exit`, `_Exit`, `_exit`|\<process.h> oder \<stdlib.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_exit.c  
// This program returns an exit code of 1. The  
// error code could be tested in a batch file.  
  
#include <stdlib.h>  
  
int main( void )  
{  
   exit( 1 );  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [_cexit, _c_exit](../../c-runtime-library/reference/cexit-c-exit.md)   
 [_exec, _wexec-Funktionen](../../c-runtime-library/exec-wexec-functions.md)   
 [_onexit, _onexit_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [quick_exit](../../c-runtime-library/reference/quick-exit1.md)   
 [_spawn, _wspawn-Funktionen](../../c-runtime-library/spawn-wspawn-functions.md)   
 [system, _wsystem](../../c-runtime-library/reference/system-wsystem.md)
