---
title: "_CrtSetDbgFlag | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtSetDbgFlag"
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
apitype: "DLLExport"
f1_keywords: 
  - "_CRTDBG_REPORT_FLAG"
  - "_CRTDBG_CHECK_EVERY_16_DF"
  - "_CRTDBG_CHECK_DEFAULT_DF"
  - "CRTDBG_CHECK_DEFAULT_DF"
  - "CRTDBG_CHECK_EVERY_128_DF"
  - "CRTDBG_CHECK_EVERY_1024_DF"
  - "_CRTDBG_CHECK_EVERY_128_DF"
  - "CrtSetDbgFlag"
  - "CRTDBG_CHECK_EVERY_16_DF"
  - "_CRTDBG_CHECK_EVERY_1024_DF"
  - "_CrtSetDbgFlag"
  - "CRTDBG_REPORT_FLAG"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CRTDBG_ALLOC_MEM_DF-Makro"
  - "_CRTDBG_CHECK_ALWAYS_DF-Makro"
  - "_CRTDBG_CHECK_CRT_DF-Makro"
  - "_CRTDBG_CHECK_DEFAULT_DF-Makro"
  - "_CRTDBG_CHECK_EVERY_1024_DF-Makro"
  - "_CRTDBG_CHECK_EVERY_128_DF-Makro"
  - "_CRTDBG_CHECK_EVERY_16_DF-Makro"
  - "_CRTDBG_DELAY_FREE_MEM_DF-Makro"
  - "_CRTDBG_REPORT_FLAG-Makro"
  - "_CrtSetDbgFlag-Funktion"
  - "CRTDBG_ALLOC_MEM_DF-Makro"
  - "CRTDBG_CHECK_ALWAYS_DF-Makro"
  - "CRTDBG_CHECK_CRT_DF-Makro"
  - "CRTDBG_CHECK_DEFAULT_DF-Makro"
  - "CRTDBG_CHECK_EVERY_1024_DF-Makro"
  - "CRTDBG_CHECK_EVERY_128_DF-Makro"
  - "CRTDBG_CHECK_EVERY_16_DF-Makro"
  - "CRTDBG_DELAY_FREE_MEM_DF-Makro"
  - "CRTDBG_REPORT_FLAG-Makro"
  - "CrtSetDbgFlag-Funktion"
ms.assetid: b5657ffb-6178-4cbf-9886-1af904ede94c
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# _CrtSetDbgFlag
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft den Zustand des **\_crtDbgFlag**\-Flags ab oder ändert ihn, um das Zuordnungsverhalten des Debugheapmanagers zu steuern \(nur Debugversion\).  
  
## Syntax  
  
```  
  
int _CrtSetDbgFlag(     int newFlag  );  
```  
  
#### Parameter  
 `newFlag`  
 Neuer Zustand für **\_crtDbgFlag**.  
  
## Rückgabewert  
 Gibt den vorherigen Zustand von **\_crtDbgFlag** zurück.  
  
## Hinweise  
 Die `_CrtSetDbgFlag`\-Funktion ermöglicht der Anwendung die Steuerung, wie der Debugheapmanager Speicherbelegungen nachverfolgt, indem die Bitfelder des **\_crtDbgFlag**\-Flags geändert werden.  Durch Einstellen \(Aktivieren\) der Bits kann die Anwendung den Debugheapmanager anweisen, spezielle Debugvorgänge durchzuführen, z. B. Überprüfen von Speicherverlusten beim Beenden der Anwendung, und einen Bericht zu erstellen, wenn Speicherverluste erkannt werden. Hierzu wird Speichermangel simuliert, indem festgelegt wird, dass die freigegebenen Speicherblöcke in der verknüpften Liste des Heaps verbleiben sollen, und indem die Integrität des Heaps durch Überprüfen jeden Speicherblocks bei jeder Belegungsanforderung verifiziert wird.  Wenn [\_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von `_CrtSetDbgFlag` während der Vorverarbeitung entfernt.  
  
 In der folgenden Tabelle werden die Bitfelder für **\_crtDbgFlag** aufgeführt und deren Verhalten beschrieben.  Da durch das Festlegen der Bits die Diagnoseausgabe erhöht und die Geschwindigkeit der Programmausführung verringert wird, sind diese Bits standardmäßig deaktiviert.  Weitere Informationen zu diesen Bitfeldern finden Sie unter [Berichtsfunktionen für den Heapzustand](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Heap_State_Reporting_Functions).  
  
|Bitfeld|Standard|Beschreibung|  
|-------------|--------------|------------------|  
|**\_CRTDBG\_ALLOC\_MEM\_DF**|ON|EIN: Aktiviert Debugheapzuordnungen und die Verwendung von Speicherblocktypbezeichnern wie `_CLIENT_BLOCK`.  AUS: Fügt neue Zuordnungen zur verknüpften Liste des Heaps hinzu, jedoch wird der Blocktyp auf **\_IGNORE\_BLOCK** festgelegt.<br /><br /> Kann auch mit einem beliebigen Heap\-Häufigkeitsüberprüfungsmakros kombiniert werden.|  
|**\_CRTDBG\_CHECK\_ALWAYS\_DF**|OFF|EIN: Bewirkt den Aufruf von [\_CrtCheckMemory](../../c-runtime-library/reference/crtcheckmemory.md) bei jeder Anforderung zur Speicherbelegung bzw. zur Aufhebung der Speicherbelegung.  AUS: `_CrtCheckMemory` muss explizit aufgerufen werden.<br /><br /> Heap\-Häufigkeitsüberprüfungsmakros haben keine Auswirkungen, wenn dieses Flag festgelegt ist.|  
|`_CRTDBG_CHECK_CRT_DF`|OFF|EIN: Schließt `_CRT_BLOCK`\-Typen bei der Erkennung von Speicherverlusten und bei Vorgängen zu Speicherzustandsunterschieden ein.  AUS: Der Speicher, der von der Laufzeitbibliothek intern verwendet wird, wird von diesen Vorgänge ignoriert.<br /><br /> Kann auch mit einem beliebigen Heap\-Häufigkeitsüberprüfungsmakros kombiniert werden.|  
|**\_CRTDBG\_DELAY\_FREE\_MEM\_DF**|OFF|EIN: Behält freigegebene Speicherblöcke in der verknüpften Liste des Heaps bei, weist sie dem **\_FREE\_BLOCK**\-Typ zu und füllt sie mit dem Bytewert "0xDD" aus.  AUS: Behält freigegebene Blöcke nicht in der verknüpften Liste des Heaps bei.<br /><br /> Kann auch mit einem beliebigen Heap\-Häufigkeitsüberprüfungsmakros kombiniert werden.|  
|`_CRTDBG_LEAK_CHECK_DF`|OFF|EIN: Führt beim Beenden des Programms eine automatische Überprüfung von Speicherverlusten durch, indem [\_CrtDumpMemoryLeaks](../../c-runtime-library/reference/crtdumpmemoryleaks.md) aufgerufen und ein Fehlerbericht generiert wird, wenn die Anwendung nicht den gesamten belegten Speicher freigeben konnte.  AUS: Führt beim Beenden des Programms keine automatische Überprüfung von Speicherverlusten durch.<br /><br /> Kann auch mit einem beliebigen Heap\-Häufigkeitsüberprüfungsmakros kombiniert werden.|  
  
 **Heap\-Häufigkeitsüberprüfungsmakros**  
  
 Sie können angeben, wie häufig die C\-Laufzeitbibliothek eine Überprüfung des Debugheaps \(`_CrtCheckMemory`\) anhand der Anzahl von Aufrufen von `malloc`, `realloc`, **free** und `_msize` ausführen soll.  
  
 `_CrtSetDbgFlag` überprüft dann die oberen 16 Bits des `newFlag`\-Parameters auf einen Wert.  Der angegebene Wert ist die Anzahl von `malloc`\-, `realloc`\-, **free**\- und `_msize`\-Aufrufen zwischen `_CrtCheckMemory`\-Aufrufen.  Vier vordefinierte Makros werden zu diesem Zweck bereitgestellt.  
  
|Makro|Anzahl von malloc\-, realloc\-, free\- und \_msize\-Aufrufen zwischen Aufrufen von \_CrtCheckMemory|  
|-----------|---------------------------------------------------------------------------------------------------------|  
|\_CRTDBG\_CHECK\_EVERY\_16\_DF|16|  
|\_CRTDBG\_CHECK\_EVERY\_128\_DF|128|  
|\_CRTDBG\_CHECK\_EVERY\_1024\_DF|1024|  
|\_CRTDBG\_CHECK\_DEFAULT\_DF|0 \(standardmäßig, keine Heapüberprüfungen\)|  
  
 Standardmäßig wird `_CrtCheckMemory` alle 1.024 Male aufgerufen, wenn Sie `malloc`, `realloc`, **free** und `_msize` aufrufen.  
  
 Beispielsweise können Sie eine Heapüberprüfung für jeden 16. `malloc`\-, `realloc`\-, **free**\- und `_msize`\-Vorgang mit dem folgenden Code festlegen:  
  
```  
#include <crtdbg.h>  
int main( )  
{  
int tmp;  
  
// Get the current bits  
tmp = _CrtSetDbgFlag(_CRTDBG_REPORT_FLAG);  
  
// Clear the upper 16 bits and OR in the desired freqency  
tmp = (tmp & 0x0000FFFF) | _CRTDBG_CHECK_EVERY_16_DF;  
  
// Set the new bits  
_CrtSetDbgFlag(tmp);  
}  
```  
  
 Die oberen 16 Bits des `newFlag`\-Parameters werden ignoriert, wenn \_CRTDBG\_CHECK\_ALWAYS\_DF angegeben wird.  In diesem Fall wird `_CrtCheckMemory` jedes Mal aufgerufen, wenn Sie `malloc`, `realloc`, **free** und `_msize` aufrufen.  
  
 `newFlag` ist der neue Zustand, der auf **\_crtDbgFlag** angewendet werden soll, und eine Kombination der Werte für jedes Bitfeld.  
  
### So ändern Sie einen oder mehrere dieser Bitfelder und erstellen einen neuen Zustand für das Flag  
  
1.  Rufen Sie `_CrtSetDbgFlag` auf, wobei der `newFlag`\-Parameter mit `_CRTDBG_REPORT_FLAG` identisch ist, um den aktuellen **\_crtDbgFlag**\-Zustand zu erhalten und den zurückgegebenen Wert in einer temporären Variablen zu speichern.  
  
2.  Aktivieren Sie die Bits durch eine `OR`\-Verknüpfung der temporären Variable mit den entsprechenden Bitmasken \(im Anwendungscode durch Manifestkonstanten dargestellt\).  
  
3.  Deaktivieren Sie die anderen Bits durch eine **AND**\-Verknüpfung mit einer bitweisen **NOT**\-Verknüpfung der entsprechenden Bitmasks.  
  
4.  Zum Festlegen des neuen Zustands für **\_crtDbgFlag** rufen Sie `_CrtSetDbgFlag` auf, wobei der `newFlag`\-Parameter mit dem in der temporären Variablen gespeicherten Wert identisch ist.  
  
 Der folgende Code zeigt, wie Speichermangel simuliert wird, indem freigegebene Speicherblöcke in der verknüpften Liste des Heaps beibehalten werden, und wie verhindert wird, dass `_CrtCheckMemory` bei jeder Belegungsanforderung aufgerufen wird:  
  
```  
// Get the current state of the flag  
// and store it in a temporary variable  
int tmpFlag = _CrtSetDbgFlag( _CRTDBG_REPORT_FLAG );  
  
// Turn On (OR) - Keep freed memory blocks in the  
// heap's linked list and mark them as freed  
tmpFlag |= _CRTDBG_DELAY_FREE_MEM_DF;  
  
// Turn Off (AND) - prevent _CrtCheckMemory from  
// being called at every allocation request  
tmpFlag &= ~_CRTDBG_CHECK_ALWAYS_DF;  
  
// Set the new state for the flag  
_CrtSetDbgFlag( tmpFlag );  
```  
  
 Eine Übersicht der Speicherverwaltung und des Debugheaps finden Sie unter [Details zum CRT\-Debugheap](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
 Zum Deaktivieren eines Flags mit der `_CrtSetDbgFlag`\-Funktion sollten Sie eine **AND**\-Verknüpfung der Variable mit einer bitweisen **NOT**\-Verknüpfung der Bitmaske verbinden.  
  
 Wenn `newFlag` kein gültiger Wert ist, ruft diese Funktion den Handler für ungültige Parameter auf, wie unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, legt diese Funktion `errno` auf `EINVAL` fest und gibt den vorherigen Zustand von `_crtDbgFlag` zurück.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_CrtSetDbgFlag`|\<crtdbg.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Nur Debugversionen von [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
  
```  
// crt_crtsetdflag.c  
// compile with: /c -D_DEBUG /MTd -Od -Zi -W3 /link -verbose:lib /debug  
/*  
 * This program concentrates on allocating and freeing memory  
 * blocks to test the functionality of the _crtDbgFlag flag..  
 */  
  
#include <string.h>  
#include <malloc.h>  
#include <crtdbg.h>  
  
int main( )  
{  
        char *p1, *p2;  
        int tmpDbgFlag;  
  
        _CrtSetReportMode( _CRT_ERROR, _CRTDBG_MODE_FILE );  
        _CrtSetReportFile( _CRT_ERROR, _CRTDBG_FILE_STDERR );  
        /*  
         * Set the debug-heap flag to keep freed blocks in the  
         * heap's linked list - This will allow us to catch any  
         * inadvertent use of freed memory  
         */  
        tmpDbgFlag = _CrtSetDbgFlag(_CRTDBG_REPORT_FLAG);  
        tmpDbgFlag |= _CRTDBG_DELAY_FREE_MEM_DF;  
        tmpDbgFlag |= _CRTDBG_LEAK_CHECK_DF;  
        _CrtSetDbgFlag(tmpDbgFlag);  
  
        /*  
         * Allocate 2 memory blocks and store a string in each  
         */  
        p1 = malloc( 34 );  
        p2 = malloc( 38 );  
        strcpy_s( p1, 34, "p1 points to a Normal allocation block" );  
        strcpy_s( p2, 38, "p2 points to a Client allocation block" );  
  
        /*  
         * Free both memory blocks  
         */  
        free( p2 );  
        free( p1 );  
  
        /*  
         * Set the debug-heap flag to no longer keep freed blocks in the  
         * heap's linked list and turn on Debug type allocations (CLIENT)  
         */  
        tmpDbgFlag = _CrtSetDbgFlag(_CRTDBG_REPORT_FLAG);  
        tmpDbgFlag |= _CRTDBG_ALLOC_MEM_DF;  
        tmpDbgFlag &= ~_CRTDBG_DELAY_FREE_MEM_DF;  
        _CrtSetDbgFlag(tmpDbgFlag);  
  
        /*  
         * Explicitly call _malloc_dbg to obtain the filename and   
         * line number of our allocation request and also so we can   
         * allocate CLIENT type blocks specifically for tracking  
         */  
        p1 = _malloc_dbg( 40, _NORMAL_BLOCK, __FILE__, __LINE__ );  
        p2 = _malloc_dbg( 40, _CLIENT_BLOCK, __FILE__, __LINE__ );  
        strcpy_s( p1, 40, "p1 points to a Normal allocation block" );  
        strcpy_s( p2, 40, "p2 points to a Client allocation block" );  
  
        /*  
         * _free_dbg must be called to free the CLIENT block  
         */  
        _free_dbg( p2, _CLIENT_BLOCK );  
        free( p1 );  
  
        /*  
         * Allocate p1 again and then exit - this will leave unfreed  
         * memory on the heap  
         */  
        p1 = malloc( 10 );  
}  
```  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)   
 [\_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)   
 [\_CrtCheckMemory](../../c-runtime-library/reference/crtcheckmemory.md)