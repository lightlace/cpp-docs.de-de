---
title: set_terminate (CRT) | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: set_terminate
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
f1_keywords: set_terminate
dev_langs: C++
helpviewer_keywords:
- set_terminate function
- terminate function
- exception handling, termination
ms.assetid: 3ff1456a-7898-44bc-9266-a328a80b6006
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 099cb340f821f04c3a5f84ccef7e3e9649482cd6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="setterminate-crt"></a>set_terminate (CRT)
Installiert Ihre Beendigungsroutine, die von `terminate` aufgerufen werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
terminate_function set_terminate(  
   terminate_function termFunction  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `termFunction`  
 Zeiger auf eine Funktion zum Beenden, die Sie schreiben.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf die vorherige Funktion zurück, die von `set_terminate` registriert wurde, sodass die vorherige Funktion später wiederhergestellt werden kann. Wenn keine vorherige Funktion festgelegt wurde, kann der Rückgabewert verwendet werden, um das Standardverhalten wiederherzustellen. Dieser Wert kann NULL sein.  
  
## <a name="remarks"></a>Hinweise  
 Die `set_terminate`-Funktion installiert `termFunction` als Funktion, die von `terminate` aufgerufen wird. `set_terminate` wird mit C++-Ausnahmebehandlung verwendet und kann an einer beliebigen Stelle im Programm aufgerufen werden, bevor die Ausnahme ausgelöst wird. `terminate` ruft standardmäßig `abort` auf. Sie können dieses Standardverhalten ändern, indem Sie eine benutzerdefinierte Beendigungsfunktion schreiben und `set_terminate` mit dem Namen Ihrer Funktion als Argument aufrufen. `terminate` ruft die letzte Funktion auf, die für `set_terminate` als Argument angegeben wurde. Nach der Ausführung aller gewünschten Bereinigungsaufgaben sollte `termFunction` das Programm beenden. Andernfalls (bei Rückgabe an den Aufrufer) wird `abort` aufgerufen.  
  
 In einer Multithreadumgebung werden die Beendigungsfunktionen für jeden Thread separat verwaltet. Jeder neue Thread muss eine eigene Beendigungsfunktion installieren. Daher ist jeder Thread für die eigene Beendigungsbehandlung verantwortlich.  
  
 Der `terminate_function`-Typ ist in EH.H als Zeiger auf eine benutzerdefinierte Beendigungsfunktion definiert, `termFunction`, die `void` zurückgibt. Ihre benutzerdefinierte Funktion `termFunction` kann keine Argumente annehmen und sollte nicht an den Aufrufer zurückgeben. Ist dies der Fall, wird `abort` aufgerufen. Eine Ausnahme kann nicht aus `termFunction` heraus ausgelöst werden.  
  
```  
typedef void ( *terminate_function )( );  
```  
  
> [!NOTE]
>  Die `set_terminate`-Funktion kann nur außerhalb des Debuggers verwendet werden.  
  
 Es gibt einen einzigen `set_terminate`-Handler für alle dynamisch verknüpften DLLs oder EXEs. Auch wenn Sie `set_terminate` aufrufen, wird Ihr Handler möglicherweise durch einen anderen ersetzt, oder Sie ersetzen einen Handler, der von einer anderen DLL oder EXE wurde.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`set_terminate`|\<eh.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
 Eine Abbildung finden Sie im Beispiel für [terminate](../../c-runtime-library/reference/terminate-crt.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Ausnahmebehandlungsroutinen](../../c-runtime-library/exception-handling-routines.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [_get_terminate](../../c-runtime-library/reference/get-terminate.md)   
 [set_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)   
 [unexpected](../../c-runtime-library/reference/unexpected-crt.md)