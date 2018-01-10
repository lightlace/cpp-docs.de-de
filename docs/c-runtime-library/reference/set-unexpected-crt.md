---
title: set_unexpected (CRT) | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: set_unexpected
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
f1_keywords: set_unexpected
dev_langs: C++
helpviewer_keywords:
- set_unexpected function
- unexpected function
- exception handling, termination
ms.assetid: ebcef032-4771-48e5-88aa-2a1ab8750aa6
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2798fff46d40ed6100f101cbc8839ad2fd166f4b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="setunexpected-crt"></a>set_unexpected (CRT)
Installiert eine eigene von `unexpected` aufzurufende Beendigungsfunktion.  
  
## <a name="syntax"></a>Syntax  
  
```  
unexpected_function set_unexpected(  
   unexpected_function unexpFunction   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `unexpFunction`  
 Zeiger auf eine Funktion, die Sie schreiben, um die `unexpected`-Funktion zu ersetzen.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf die vorherige Beendigungsfunktion zurück, die von `_set_unexpected` registriert wurde, sodass die vorherige Funktion später wiederhergestellt werden kann. Wenn keine vorherige Funktion festgelegt wurde, kann der Rückgabewert verwendet werden, um das Standardverhalten wiederherzustellen. Dieser Wert kann NULL sein.  
  
## <a name="remarks"></a>Hinweise  
 Die `set_unexpected`-Funktion installiert `unexpFunction` als die von `unexpected` aufgerufene Funktion. `unexpected` wird in der aktuellen C++-Ausnahmebehandlungsimplementierung nicht verwendet. Der `unexpected_function`-Typ ist in EH.H als Zeiger auf eine benutzerdefinierte unerwartete Funktion, `unexpFunction`, definiert, die `void` zurückgibt. Ihre benutzerdefinierte `unexpFunction`-Funktion sollte nicht an ihren Aufrufer zurückgeben.  
  
```  
typedef void ( *unexpected_function )( );  
```  
  
 Standardmäßig ruft `unexpected` `terminate` auf. Sie können das Standardverhalten ändern, indem Sie Ihre eigene Terminierungsfunktion schreiben und `set_unexpected` mit dem Namen der Funktion als Argument aufrufen. Die `unexpected`-Routine ruft immer die letzte Funktion auf, die für `set_unexpected` als Argument angegeben wurde.  
  
 Anders als die benutzerdefinierte Funktion, die durch einen Aufruf an `set_terminate` installiert wurde, kann aus `unexpFunction` heraus eine Ausnahme ausgelöst werden.  
  
 In einer Multithreadumgebung werden unerwartete Funktionen für jeden Thread separat verwaltet. Jeder neue Thread muss eine eigene unerwartete Funktion installieren. Daher ist jeder Thread für die eigene unerwartete Behandlung verantwortlich.  
  
 In der aktuellen Microsoft-Implementierung der C++-Ausnahmebehandlung ruft `unexpected` standardmäßig `terminate` auf und wird nie von der Laufzeitbibliothek für die Ausnahmebehandlung aufgerufen. Der Aufruf von `unexpected` anstelle von `terminate` bietet keine besonderen Vorteile.  
  
 Es gibt einen einzigen `set_unexpected`-Handler für alle dynamisch verknüpften DLLs oder EXEs. Auch wenn Sie `set_unexpected` aufrufen, wird Ihr Handler möglicherweise durch einen anderen ersetzt, oder Sie ersetzen einen Handler, der von einer anderen DLL oder EXE festgelegt wurde.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`set_unexpected`|\<eh.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="see-also"></a>Siehe auch  
 [Ausnahmebehandlungsroutinen](../../c-runtime-library/exception-handling-routines.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [_get_unexpected](../../c-runtime-library/reference/get-unexpected.md)   
 [set_terminate](../../c-runtime-library/reference/set-terminate-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)   
 [unexpected](../../c-runtime-library/reference/unexpected-crt.md)