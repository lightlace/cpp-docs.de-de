---
title: set_terminate (CRT) | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- set_terminate
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
- set_terminate
dev_langs:
- C++
helpviewer_keywords:
- set_terminate function
- terminate function
- exception handling, termination
ms.assetid: 3ff1456a-7898-44bc-9266-a328a80b6006
caps.latest.revision: 13
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
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 657c03ebed8e077e3a6c2eac96eae264f4a19998
ms.lasthandoff: 02/24/2017

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
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`set_terminate`|\<eh.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
 Eine Abbildung finden Sie im Beispiel für [terminate](../../c-runtime-library/reference/terminate-crt.md).  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Siehe auch  
 [Ausnahmebehandlungsroutinen](../../c-runtime-library/exception-handling-routines.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [_get_terminate](../../c-runtime-library/reference/get-terminate.md)   
 [set_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)   
 [unexpected](../../c-runtime-library/reference/unexpected-crt.md)
