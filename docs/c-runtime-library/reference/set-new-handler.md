---
title: _set_new_handler | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 17
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: c8a3b6e7df9f46ebf299f2fe5472461f1944b055
ms.contentlocale: de-de
ms.lasthandoff: 04/04/2017

---
# <a name="setnewhandler"></a>_set_new_handler
Übergibt die Steuerung an den Fehlerbehandlungsmechanismus, wenn der `new`-Operator keine Speicherbelegung vornehmen kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
_PNH _set_new_handler(  
   _PNH pNewHandler   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pNewHandler`  
 Zeiger zu der von der Anwendung bereitgestellten Speicherbehandlungsfunktion. Ist das Argument 0, wird der neue Ereignishandler entfernt.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger zu der vorherigen Ausnahmebehandlungsfunktion zurück, die von `_set_new_handler` registriert wurde, sodass die vorherige Funktion später wiederhergestellt werden kann. Wenn keine vorherige Funktion festgelegt wurde, kann der Rückgabewert verwendet werden, um das Standardverhalten wiederherzustellen. Dieser Wert kann `NULL` sein.  
  
## <a name="remarks"></a>Hinweise  
 Mit der C++-Funktion `_set_new_handler` wird eine Funktion für die Ausnahmebehandlung angegeben, die die Steuerung übernimmt, wenn der `new`-Operator keinen Arbeitsspeicher zuordnen kann. Wenn `new` fehlschlägt, ruft das Laufzeitsystem automatisch die Ausnahmebehandlungsfunktion auf, die als Argument an `_set_new_handler` übergeben wurde. `_PNH`, in New.h definiert, ist ein Zeiger auf eine Funktion mit dem Rückgabetyp `int` und verwendet ein Argument vom Typ `size_t`. Geben Sie mithilfe von `size_t` den zuzuordnenden Speicherplatz an.  
  
 Es ist kein Standardhandler vorhanden.  
  
 `_set_new_handler` ist im Wesentlichen ein Garbage Collection-Schema. Das Laufzeitsystem wiederholt die Zuordnung jedes Mal, wenn die Funktion einen Wert ungleich null zurückgibt, und schlägt fehl, wenn die Funktion 0 zurückgibt.  
  
 Ein Vorkommen der `_set_new_handler`-Funktion in einem Programm registriert die Ausnahmebehandlungsfunktion, die in der Argumentliste mit dem Laufzeitsystem angegeben wird:  
  
```  
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
  
 Sie können die Adresse der Funktion speichern, die zuletzt an die `_set_new_handler`-Funktion, übergeben wurde, und sie später reaktivieren:  
  
```  
_PNH old_handler = _set_new_handler( my_handler );  
   // Code that requires my_handler  
   _set_new_handler( old_handler )  
   // Code that requires old_handler  
```  
  
 Die C++-Funktion [_set_new_mode](../../c-runtime-library/reference/set-new-mode.md) legt den neuen Handlermodus für [malloc](../../c-runtime-library/reference/malloc.md) fest. Der neue Handlermodus gibt an, ob bei einem Fehler `malloc` die neue Handlerroutine aufrufen soll, wie dies von `_set_new_handler` festgelegt ist. Standardmäßig ruft `malloc` bei einem Speicherbelegungsfehler nicht die neue Handlerroutine auf. Sie können dieses Standardverhalten überschreiben, sodass, wenn `malloc` Speicher nicht belegen kann,`malloc` die neue Handlerroutine genauso aufruft wie der `new`-Operator, wenn dieser aus demselben Grund fehlschlägt. Um den Standardwert zu überschreiben, rufen Sie  
  
```  
_set_new_mode(1)  
```  
  
 rechtzeitig im Programm auf, oder stellen Sie eine Verknüpfung mit Newmode.obj her.  
  
 Wenn Sie eine benutzerdefinierte `operator new` angegeben wird, nicht automatisch die neue Handlerfunktionen bei einem Fehler aufgerufen werden.  
  
 Weitere Informationen finden Sie unter [new](../../cpp/new-operator-cpp.md) und [delete](../../cpp/delete-operator-cpp.md) in der *C++-Sprachreferenz*.  
  
 Es gibt einen einzigen `_set_new_handler`-Handler für alle dynamisch verknüpften DLLs oder ausführbaren Dateien. Auch wenn Sie `_set_new_handler` aufrufen, wird Ihr Handler möglicherweise durch einen anderen ersetzt, oder Sie ersetzen einen Handler, der von einer anderen DLL oder ausführbaren Datei festgelegt wurde.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_set_new_handler`|\<new.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
 Wenn – wie in diesem Beispiel – die Zuordnung fehlschlägt, wird die Steuerung an MyNewHandler übergeben. Das an MyNewHandler übergebene Argument ist die Anzahl der angeforderten Bytes. Der von MyNewHandler zurückgegebene Wert ist ein Flag, das angibt, ob die Zuordnung wiederholt werden soll: Ein Wert ungleich null gibt an, dass die Zuordnung wiederholt werden soll, und der Wert 0 gibt an, dass die Verteilung fehlgeschlagen ist.  
  
```  
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
 [Speicherbelegung](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)
