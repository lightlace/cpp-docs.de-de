---
title: _aligned_msize_dbg | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _aligned_msize_dbg
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
- _aligned_msize_dbg
dev_langs:
- C++
helpviewer_keywords:
- _aligned_msize_dbg
ms.assetid: f1c44af0-3f66-4033-81d1-d71d3afecba0
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 84964b0a49b236bae056125de8155b18880eb378
ms.openlocfilehash: 10449c1d6651f4816e3f1f6ab7c406abc070b7a4
ms.lasthandoff: 02/24/2017

---
# <a name="alignedmsizedbg"></a>_aligned_msize_dbg
Gibt die Größe eines im Heap belegten Speicherblocks zurück (nur Debugversion).  
  
## <a name="syntax"></a>Syntax  
  
```  
size_t _aligned_msize_dbg(  
   void *memblock,  
   size_t alignment,  
   size_t offset  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `memblock`  
 Zeiger zum Speicherblock.  
  
 [in] `alignment`  
 Der Ausrichtungswert, der eine ganzzahlige Potenz von 2 sein muss.  
  
 [in] `offset`  
 Der Offset in der Speicherbelegung zum Erzwingen der Ausrichtung.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt die Größe (in Bytes) als ganze Zahl ohne Vorzeichen zurück.  
  
## <a name="remarks"></a>Hinweise  
 Die `alignment`- und `offset`-Werte müssen mit den Werten identisch sein, die an die Funktion übergeben wurden, die den Speicherblock belegt hat.  
  
 `_aligned_msize_dbg` ist eine Debugversion der [_aligned_msize](../../c-runtime-library/reference/aligned-msize.md)-Funktion. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, wird jeder Aufruf von `_aligned_msize_dbg` zu einem Aufruf von `_aligned_msize` reduziert. `_aligned_msize` und `_aligned_msize_dbg` berechnen die Größe eines Speicherblocks im Basisheap, jedoch fügt `_aligned_msize_dbg` eine Debugfunktionen hinzu: Es schließt die Puffer auf beiden Seiten des Benutzerteils des Speicherblocks in der zurückgegebenen Größe ein.  
  
 Diese Funktion überprüft seine Parameter. Wenn `memblock` ein NULL-Zeiger oder `alignment` keine Potenz von 2 ist, ruft `_msize` einen Handler für ungültige Parameter auf, wie in unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn der Fehler behandelt wird, legt die Funktion `errno` auf `EINVAL` fest und gibt -1 zurück.  
  
 Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details (CRT Debug Heap-Details)](/visualstudio/debugger/crt-debug-heap-details). Informationen zu den Belegungsblocktypen und ihrer Verwendung finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details). Weitere Informationen zu den Unterschieden zwischen dem Aufruf einer Standardheapfunktion und ihrer Debugversion in einem Debugbuild einer Anwendung finden Sie unter [Debugversionen von Heapbelegungsfunktionen](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_aligned_msize_dbg`|\<crtdbg.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="libraries"></a>Bibliotheken  
 Nur Debugversionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md)  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Siehe auch  
 [Speicherbelegung](../../c-runtime-library/memory-allocation.md)
