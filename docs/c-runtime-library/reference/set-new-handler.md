---
title: "_set_new_handler"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_set_new_handler"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_set_new_handler"
  - "set_new_handler"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_set_new_handler-Funktion"
  - "Fehlerbehandlung"
  - "set_new_handler-Funktion"
  - "Transformieren der Steuerung zum Fehlerhandler"
ms.assetid: 1d1781b6-5cf8-486a-b430-f365e0bb023f
caps.latest.revision: 17
caps.handback.revision: "15"
ms.author: "corob"
manager: "ghogen"
---
# _set_new_handler
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Übergibt die Steuerung an den Fehlerbehandlungsmechanismus, wenn der `new`\-Operator keine Speicherbelegung vornehmen kann.  
  
## Syntax  
  
```  
_PNH _set_new_handler(  
   _PNH pNewHandler   
);  
```  
  
#### Parameter  
 `pNewHandler`  
 Zeiger auf die von der Anwendung bereitgestellten Arbeitsspeicherbehandlungsfunktion.  Ein Argument von 0 wird der neuen Handler entfernt werden.  
  
## Rückgabewert  
 Gibt einen Zeiger zur vorherigen Ausnahmebehandlungsfunktion zurück, die von `_set_new_handler` registriert wird, dass die vorherige Funktion später wiederhergestellt werden kann.  Wenn keine vorherige Funktion festgelegt wurde, kann der Rückgabewert verwendet werden, um das Standardverhalten wiederherzustellen; kann dieser Wert `NULL` sein.  
  
## Hinweise  
 Die Funktion C\+\+ `_set_new_handler` gibt eine Ausnahmebehandlungsfunktion dass Gewinnsteuerelement an, wenn der `new`\-Operator Belegen nicht kann.  Wenn `new` fehlschlägt, ruft das Laufzeitsystem automatisch die Ausnahmebehandlungsfunktion auf, die als Argument an `_set_new_handler` übergeben wurde.  `_PNH`, die in New.h, ist ein Zeiger auf eine Funktion zurückgibt, dass `int` eingeben und akzeptiert ein Argument des Typs `size_t`.  Verwenden Sie `size_t`, um den Platz zugeordnet werden, anzugeben.  
  
 Es gibt keinen Standardhandler.  
  
 `_set_new_handler` ist im Wesentlichen ein Garbage Collections\-Schema.  Das Laufzeitsystem versucht Zuordnung, wenn die Funktion einen Wert ungleich 0 \(null\) zurückgibt erneut und schlägt wenn die Funktion 0 aus.  
  
 Ein Vorkommen der `_set_new_handler`\-Funktion in den Registern eines Programms, die die Ausnahmebehandlungsfunktion in der Argumentliste durch das Laufzeitsystem angegeben:  
  
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
  
 Sie können die Funktionsadresse speichern, die zuletzt in `_set_new_handler`\-Funktion übergeben wurde und später erneut eingefügt:  
  
```  
_PNH old_handler = _set_new_handler( my_handler );  
   // Code that requires my_handler  
   _set_new_handler( old_handler )  
   // Code that requires old_handler  
```  
  
 Die Funktion C\+\+ [\_set\_new\_mode](../../c-runtime-library/reference/set-new-mode.md) legt den neuen Handlermodus für [malloc](../../c-runtime-library/reference/malloc.md) fest.  Der neue Handlermodus gibt an, dass, auf Fehler, `malloc`, die neue Handlerroutine wie Sie von `_set_new_handler` aufzurufen ist.  Standardmäßig ruft `malloc` bei einem Speicherbelegungsfehler nicht die neue Handlerroutine auf.  Sie können dieses Standardverhalten überschreiben, sodass, wenn `malloc` Speicher nicht belegen kann,`malloc` die neue Handlerroutine genauso aufruft wie der `new`\-Operator, wenn dieser aus demselben Grund fehlschlägt.  Um den Standardwert überschreibt, rufen Sie auf:  
  
```  
_set_new_mode(1)  
```  
  
 frühzeitig im Programm oder in Link mit Newmode.obj.  
  
 Wenn benutzerdefinierte `operator new` bereitgestellt wird, werden die neuen Handlerfunktionen nicht automatisch ersuchter Fehler.  
  
 Weitere Informationen finden Sie unter [neu](../../cpp/new-operator-cpp.md) und [löschen](../../cpp/delete-operator-cpp.md) der *C\+\+\-Sprachreferenz*.  
  
 Es gibt einen einzelnen `_set_new_handler`\-Handler für alle dynamisch verknüpfte DLLs oder ausführbaren Dateien; wenn Sie `_set_new_handler` aufrufen, wird der Handler ersetzt durch andere möglicherweise, das oder ersetzen Sie einen Handler, der von einer anderen DLL oder ausführbare Datei festgelegt wird.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_set_new_handler`|\<new.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
 In diesem Beispiel die Zuordnung fehlschlägt, wird MyNewHandler Steuerelement zu übertragen.  Das Argument, das an MyNewHandler übergeben wird, ist die Anzahl von Bytes angefordert.  Der Wert, der von MyNewHandler zurückgegeben wird, ist ein zugewiesenes Flag, ob Zuordnung wiederholt werden soll: ein Wert ungleich 0 \(null\) gibt an, dass Zuordnung wiederholt werden soll, und bei einem Wert 0 \(null\) gibt an, dass Zuordnung fehlgeschlagen ist.  
  
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
  
  **Zuordnung verlassen.  Verschmelzender Heap.**  
**Diese Anwendung hat ein nicht ordnungsgemäßes Beenden der Runtime angefordert.**  
**Weitere Informationen erhalten Sie von dem für die Anwendung zuständigen Supportteam.**    
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Speicherbelegung](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)