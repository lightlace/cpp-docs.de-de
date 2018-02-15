---
title: _CrtIsMemoryBlock | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _CrtIsMemoryBlock
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
f1_keywords:
- CrtlsMemoryBlock
- _CrtIsMemoryBlock
dev_langs:
- C++
helpviewer_keywords:
- _CrtIsMemoryBlock function
- CrtIsMemoryBlock function
ms.assetid: f7cbbc60-3690-4da0-a07b-68fd7f250273
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 58faccd95e831dd264910abf063529db12701bf6
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="crtismemoryblock"></a>_CrtIsMemoryBlock
Überprüft, ob sich ein angegebener Speicherblock im lokalen Heap befindet und ob er einen gültigen Debugheap-Blocktypbezeichner hat (nur Debugversion).  
  
## <a name="syntax"></a>Syntax  
  
```  
int _CrtIsMemoryBlock(   
   const void *userData,  
   unsigned int size,  
   long *requestNumber,  
   char **filename,  
   int *linenumber   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `userData`  
 Zeiger auf den Anfang des zu überprüfenden Speicherblocks.  
  
 [in] `size`  
 Größe des angegebenen Blocks (in Bytes).  
  
 [out] `requestNumber`  
 Zeiger zur Belegungsnummer des Blocks oder `NULL`.  
  
 [out] `filename`  
 Zeiger zum Namen der Quelldatei, der den Block angefordert hat, oder `NULL`.  
  
 [out] `linenumber`  
 Zeiger zur Zeilennummer in der Quelldatei oder `NULL`.  
  
## <a name="return-value"></a>Rückgabewert  
 `_CrtIsMemoryBlock` gibt `TRUE` zurück, wenn sich der angegebene Speicherblock im lokalen Heap befindet und über einen gültigen Debugheap-Blocktypbezeichner verfügt. Andernfalls gibt die Funktion `FALSE` zurück.  
  
## <a name="remarks"></a>Hinweise  
 Die `_CrtIsMemoryBlock`-Funktion überprüft, ob sich ein angegebener Speicherblock im lokalen Heap der Anwendung befindet und ob sie einen gültigen Blocktypbezeichner hat. Diese Funktion kann auch verwendet werden, um die Bestellnummer der Objektzuordnung und den Quelldateinamen/die Zeilennummer abzurufen, wo die Speicherblockbelegung ursprünglich angefordert wurde. Die Übergabe von Werten ungleich NULL für den `requestNumber`-, `filename`- oder `linenumber`-Parameter führt dazu, dass `_CrtIsMemoryBlock` diese Parameter auf die Werte im Debugheader des Speicherblocks festlegt, wenn der Block im lokalen Heap gefunden wird. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von `_CrtIsMemoryBlock` während der Vorverarbeitung entfernt.  
  
 Wenn `_CrtIsMemoryBlock` fehlschlägt, wird `FALSE` zurückgegeben und die Ausgabeparameter werden auf die Standardwerte initialisiert: `requestNumber` und `lineNumber` werden auf 0 und `filename` wird auf `NULL` eingestellt.  
  
 Da diese Funktion `TRUE` oder `FALSE` zurückgibt, kann sie an eine der [_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)-Makros übergeben werden, um einen einfachen Debug-Fehlerbehandlungsmechanismus zu erstellen. Im folgenden Beispiel wird ein Assertionsfehler ausgelöst, wenn sich die angegebene Adresse nicht im lokalen Heap befindet:  
  
```  
_ASSERTE( _CrtIsMemoryBlock( userData, size, &requestNumber,   
&filename, &linenumber ) );  
```  
  
 Weitere Informationen dazu, wie `_CrtIsMemoryBlock` mit anderen Debugfunktionen und -makros verwendet werden kann, finden Sie unter [Makros für die Berichterstellung](/visualstudio/debugger/macros-for-reporting). Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_CrtIsMemoryBlock`|\<crtdbg.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="libraries"></a>Bibliotheken  
 Nur Debugversionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Beispiel  
 Weitere Informationen hierzu finden Sie im Beispiel für das Thema [_CrtIsValidHeapPointer](../../c-runtime-library/reference/crtisvalidheappointer.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)