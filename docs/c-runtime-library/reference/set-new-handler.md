---
title: _set_new_handler | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _set_new_handler
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
- _set_new_handler
- set_new_handler
dev_langs:
- C++
helpviewer_keywords:
- _set_new_handler function
- set_new_handler function
- error handling
- transferring control to error handler
ms.assetid: 1d1781b6-5cf8-486a-b430-f365e0bb023f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 30cd0c2a991ec046b0b1f55100c58641833cb992
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="setnewhandler"></a>_set_new_handler

Überträgt die Steuerung an die Fehlerbehandlungsmechanismus Wenn die **neue** -Operator keine speicherbelegung vornehmen kann.

## <a name="syntax"></a>Syntax

```cpp
_PNH _set_new_handler( _PNH pNewHandler );
```

### <a name="parameters"></a>Parameter

*pNewHandler*<br/>
Zeiger zu der von der Anwendung bereitgestellten Speicherbehandlungsfunktion. Ist das Argument 0, wird der neue Ereignishandler entfernt.

## <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf die vorhergehende Ausnahme Funktion registriert, indem Sie zur Behandlung **_set_new_handler**, sodass die vorherige Funktion später wiederhergestellt werden kann. Wenn keine previous-Funktion festgelegt wurde, kann der Rückgabewert verwendet werden, um das Standardverhalten wiederherstellen; Mögliche Werte sind **NULL**.

## <a name="remarks"></a>Hinweise

Die C++ **_set_new_handler** Funktion gibt eine Ausnahmebehandlung-Funktion, die Steuerung übernimmt, wenn die **neue** -Operator keine speicherbelegung vornehmen kann. Wenn **neue** ein Fehler auftritt, ruft das Laufzeitsystem automatisch die Ausnahmebehandlung-Funktion, die als Argument übergeben wurde **_set_new_handler**. **_PNH**, in New.h definiert wird, ist ein Zeiger auf eine Funktion, die Typ zurückgibt **Int** und nutzt ein Argument des Typs **Size_t**. Verwendung **Size_t** an die Menge des Speicherplatzes zugeordnet werden soll.

Es ist kein Standardhandler vorhanden.

**_set_new_handler** ist im Wesentlichen eine Garbage Collection-Schema. Das Laufzeitsystem wiederholt die Zuordnung jedes Mal, wenn die Funktion einen Wert ungleich null zurückgibt, und schlägt fehl, wenn die Funktion 0 zurückgibt.

Ein Vorkommen von der **_set_new_handler** -Funktion in einem Programm registriert die Ausnahmebehandlung-Funktion, die in der Argumentliste, mit dem System zur Laufzeit angegeben:

```cpp
// set_new_handler1.cpp
#include <new.h>

int handle_program_memory_depletion( size_t )
{
   // Your code
}

int main( void )
{
   _set_new_handler( handle_program_memory_depletion );
   int *pi = new int[BIG_NUMBER];
}
```

Sie können die Funktionsadresse, die zuletzt an speichern die **_set_new_handler** -Funktion und später wieder zu aktivieren:

```cpp
   _PNH old_handler = _set_new_handler( my_handler );
   // Code that requires my_handler
   // . . .
   _set_new_handler( old_handler )
   // Code that requires old_handler
   // . . .
```

Die C++-Funktion [_set_new_mode](set-new-mode.md) legt den neuen Handlermodus für [malloc](malloc.md) fest. Der neue handlermodus gibt an, ob bei einem Fehler **"malloc"** ist, rufen Sie die neue Handlerroutine Isolationstransaktionen gemäß **_set_new_handler**. Standardmäßig **"malloc"** auf bei einem speicherbelegungsfehler nicht die neue Handlerroutine aufgerufen. Sie können dieses Standardverhalten überschreiben, damit, wenn **"malloc"** Arbeitsspeicher nicht belegen kann **"malloc"** die neue Handlerroutine genauso aufruft wie der **neue** Operator ist. Wenn dieser aus demselben Grund fehlschlägt. Um den Standardwert zu überschreiben, rufen Sie

```cpp
_set_new_mode(1);
```

rechtzeitig im Programm auf, oder stellen Sie eine Verknüpfung mit Newmode.obj her.

Wenn Sie eine benutzerdefinierte `operator new` angegeben wird, nicht automatisch die neue Handlerfunktionen bei einem Fehler aufgerufen werden.

Weitere Informationen finden Sie unter [new](../../cpp/new-operator-cpp.md) und [delete](../../cpp/delete-operator-cpp.md) in der *C++-Sprachreferenz*.

Es gibt einen einzigen **_set_new_handler** Handler für alle dynamisch verknüpften DLLs oder ausführbaren Dateien; auch wenn Sie aufgerufen **_set_new_handler** Ihr Handler möglicherweise durch eine andere ersetzt werden, oder, die Sie ersetzen einen Handler, die von einer anderen DLL oder ausführbare Datei festgelegt werden.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_set_new_handler**|\<new.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Wenn – wie in diesem Beispiel – die Zuordnung fehlschlägt, wird die Steuerung an MyNewHandler übergeben. Das an MyNewHandler übergebene Argument ist die Anzahl der angeforderten Bytes. Der von MyNewHandler zurückgegebene Wert ist ein Flag, das angibt, ob die Zuordnung wiederholt werden soll: Ein Wert ungleich null gibt an, dass die Zuordnung wiederholt werden soll, und der Wert 0 gibt an, dass die Verteilung fehlgeschlagen ist.

```cpp
// crt_set_new_handler.cpp
// compile with: /c
#include <stdio.h>
#include <new.h>
#define BIG_NUMBER 0x1fffffff

int coalesced = 0;

int CoalesceHeap()
{
   coalesced = 1;  // Flag RecurseAlloc to stop
   // do some work to free memory
   return 0;
}
// Define a function to be called if new fails to allocate memory.
int MyNewHandler( size_t size )
{
   printf("Allocation failed. Coalescing heap.\n");

   // Call a function to recover some heap space.
   return CoalesceHeap();
}

int RecurseAlloc() {
   int *pi = new int[BIG_NUMBER];
   if (!coalesced)
      RecurseAlloc();
   return 0;
}

int main()
{
   // Set the failure handler for new to be MyNewHandler.
   _set_new_handler( MyNewHandler );
   RecurseAlloc();
}
```

```Output
Allocation failed. Coalescing heap.

This application has requested the Runtime to terminate it in an unusual way.
Please contact the application's support team for more information.
```

## <a name="see-also"></a>Siehe auch

[Speicherreservierung](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[free](free.md)<br/>
[realloc](realloc.md)<br/>
