---
title: ___setlc_active_func, ___unguarded_readlc_active_add_func | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- ___setlc_active_func
- ___unguarded_readlc_active_add_func
apilocation:
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr110.dll
- msvcr80.dll
- msvcr120.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- ___unguarded_readlc_active_add_func
- ___setlc_active_func
dev_langs:
- C++
helpviewer_keywords:
- ___setlc_active_func
- ___unguarded_readlc_active_add_func
ms.assetid: 605ec4e3-81e5-4ece-935a-f434768cc702
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 532aac2e47a402ae04ba4d4bf4fcb133c997bd31
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="setlcactivefunc-unguardedreadlcactiveaddfunc"></a>___setlc_active_func, ___unguarded_readlc_active_add_func
VERALTET. Die CRT exportiert diese internen Funktionen nur zur Aufrechterhaltung der Binärkompatibilität.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
int ___setlc_active_func(void);  
int * ___unguarded_readlc_active_add_func(void);  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Der zurückgegebene Wert ist nicht signifikant.  
  
## <a name="remarks"></a>Hinweise  
 Obwohl die internen CRT-Funktionen `___setlc_active_func` und `___unguarded_readlc_active_add_func` veraltet sind und nicht mehr verwendet werden, werden sie von der CRT-Bibliothek exportiert, um die Binärkompatibilität aufrechtzuerhalten. Der ursprüngliche Zweck von `___setlc_active_func` war, die Anzahl der aktuell aktiven Rufe an die Funktion `setlocale` zurückzugeben. Der ursprüngliche Zweck von `___unguarded_readlc_active_add_func` war, die Anzahl der Funktionen auszugeben, die auf das Gebietsschema verwiesen, ohne es zu sperren.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`___setlc_active_func`, `___unguarded_readlc_active_add_func`|Keine|  
  
## <a name="see-also"></a>Siehe auch  
 [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)