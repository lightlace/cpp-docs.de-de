---
title: _execute_onexit_table, _initialize_onexit_table, _register_onexit_function | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _execute_onexit_table
- _initialize_onexit_table
- _register_onexit_function
apilocation:
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _execute_onexit_table
- process/_execute_onexit_table
- _initialize_onexit_table
- process/_initialize_onexit_table
- _register_onexit_function
- process/_register_onexit_function
dev_langs:
- C++
helpviewer_keywords:
- _execute_onexit_table function
- _initialize_onexit_table function
- _register_onexit_function function
ms.assetid: ad9e4149-d4ad-4fdf-aaaf-cf786fcb4473
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d2aa296c04d81fcdea2000ab8e2dbc1ae5523673
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="executeonexittable-initializeonexittable-registeronexitfunction"></a>_execute_onexit_table, _initialize_onexit_table, _register_onexit_function
Verwaltet die Routinen, die zum Zeitpunkt der Beendigung aufgerufen werden sollen.  
  
## <a name="syntax"></a>Syntax  
  
```  
int _initialize_onexit_table(  
    _onexit_table_t* table  
    );  
  
int _register_onexit_function(  
    _onexit_table_t* table,  
    _onexit_t        function  
    );  
  
int _execute_onexit_table(  
    _onexit_table_t* table  
    );  
```  
  
#### <a name="parameters"></a>Parameter  
 [inout] `table`  
 Ein Zeiger auf die onexit-Funktionstabelle.  
  
 [in] `function`  
 Ein Zeiger auf eine Funktion zum Hinzufügen zur onexit-Funktionstabelle.  
  
## <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall wird 0 zurückgegeben. Andernfalls wird ein negativer Wert zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktionen sind Details zur Implementierung der Infrastruktur und unterstützen die C-Laufzeit. Sie sollten nicht direkt aus Ihrem Code aufgerufen werden. Die C-Laufzeit verwendet eine *onexit-Funktionstabelle* zum Darstellen einer Sequenz von Funktionen, die durch Aufrufe von `atexit`, `at_quick_exit` und `_onexit` registriert werden. Die Datenstruktur der onexit-Funktionstabelle ist ein undurchsichtiges Implementierungsdetail der C-Laufzeit; die Reihenfolge und Bedeutung der Datenmember ändert sich möglicherweise. Sie sollten nicht durch externen Code überprüft werden.  
  
 Die Funktion `_initialize_onexit_table` initialiseirt die onexit-Funktionstabelle auf ihren Anfangswert.  Diese Funktion muss aufgerufen werden bevor die onexit-Funktionstabelle an entweder `_register_onexit_function` oder `_execute_onexit_table` weitergegeben wird.  
  
 Die `_register_onexit_function` Funktion fügt eine Funktion an das Ende der onexit-Funktionstabelle an.  
  
 Die Funktion `_execute_onexit_table` führt alle Funktionen in der onexit-Funktion-Tabelle aus, löscht die Tabelle, und gibt dann zurück. Nach Aufruf von `_execute_onexit_table` befindet sich die Tabelle in einem ungültigen Zustand. Sie muss durch einen Aufruf von `_initialize_onexit_table` neu initialisiert werden, bevor sie erneut verwendet wird.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_initialize_onexit_table function`, `_register_onexit_function`, `_execute_onexit_table`|C, C++: \<process.h>|  
  
 Die Funktionen `_initialize_onexit_table`, `_register_onexit_function` und `_execute_onexit_table` sind Microsoft-spezifisch. Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [atexit](../c-runtime-library/reference/atexit.md)   
 [exit, _Exit, _exit](../c-runtime-library/reference/exit-exit-exit.md)   
 [_onexit, _onexit_m](../c-runtime-library/reference/onexit-onexit-m.md)