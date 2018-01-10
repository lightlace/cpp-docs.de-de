---
title: _CrtMemDumpAllObjectsSince | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _CrtMemDumpAllObjectsSince
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
- CrtMemDumpAllObjectsSince
- _CrtMemDumpAllObjectsSince
dev_langs: C++
helpviewer_keywords:
- _CrtMemDumpAllObjectsSince function
- CrtMemDumpAllObjectsSince function
ms.assetid: c48a447a-e6bb-475c-9271-a3021182a0dc
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d71b5d13b5616717c0b3fc0ac6eae0fc1ca8b551
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="crtmemdumpallobjectssince"></a>_CrtMemDumpAllObjectsSince
Gibt Informationen zu Objekten im Heap ab Beginn der Programmausführung oder ab einem angegebenen Heapzustand aus (nur Debugversion).  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      void _CrtMemDumpAllObjectsSince(   
   const _CrtMemState *state   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `state`  
 Zeiger zum Heapzustand, ab dem die Ausgabe erfolgen soll, oder **NULL**  
  
## <a name="remarks"></a>Hinweise  
 Die `_CrtMemDumpAllObjectsSince`-Funktion gibt die Debugheaderinformationen von Objekten, die im Heap zugeordnet sind, in einer für den Benutzer lesbaren Formular aus. Die Dumpinformationen können von der Anwendung zum Nachverfolgen von Zuordnungen und zum Erkennen von Speicherproblemen verwendet werden. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von `_CrtMemDumpAllObjectsSince` während der Vorverarbeitung entfernt.  
  
 `_CrtMemDumpAllObjectsSince` verwendet den Wert des `state`-Parameters, um zu ermitteln, wo der Dumpvorgang initiiert werden soll. Um die Ausgabe ab einem angegebenen Heapzustand zu beginnen, muss der `state`-Parameter ein Zeiger zu einer **_CrtMemState**-Struktur sein, die vor dem Aufruf von [ durch ](../../c-runtime-library/reference/crtmemcheckpoint.md)_CrtMemCheckpoint`_CrtMemDumpAllObjectsSince` gefüllt wurde. Wenn der `state`-Parameter **NULL** ist, startet die Funktion die Ausgabe ab Beginn der Programmausführung.  
  
 Wenn die Anwendung eine Dumphookfunktion durch Aufrufen von [_CrtSetDumpClient](../../c-runtime-library/reference/crtsetdumpclient.md) installiert hat, wird die von der Anwendung bereitgestellte Dumpfunktion ebenfalls aufgerufen, wenn `_CrtMemDumpAllObjectsSince` Informationen zu einem `_CLIENT_BLOCK`-Blocktyp ausgibt. Standardmäßig sind interne C-Laufzeitblöcke (`_CRT_BLOCK`) nicht in Speicherabbildvorgängen enthalten. Die [_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md)-Funktion kann zum Aktivieren des `_CRTDBG_CHECK_CRT_DF`-Bits von **_crtDbgFlag** verwendet werden, um diese Blöcke einzuschließen. Außerdem werden die Blöcke, die als „freigegeben“ oder „ignoriert“ markiert wurden (**_FREE_BLOCK**, **_IGNORE_BLOCK**) nicht im Speicherabbild berücksichtigt.  
  
 Weitere Informationen über Heapzustandsfunktionen und die `_CrtMemState`-Struktur finden Sie unter [Berichtsfunktionen für den Heapzustand](/visualstudio/debugger/crt-debug-heap-details). Weitere Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|**_CrtMemDumpAll-ObjectsSince**|\<crtdbg.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="libraries"></a>Bibliotheken  
 Nur Debugversionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Beispiel  
 Ein Beispiel für die Verwendung von `_CrtMemDumpAllObjectsSince` finden Sie unter [crt_dbg2](http://msdn.microsoft.com/en-us/21e1346a-6a17-4f57-b275-c76813089167).  
  
## <a name="see-also"></a>Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)   
 [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)