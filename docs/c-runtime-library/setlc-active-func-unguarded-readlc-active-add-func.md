---
title: ___setlc_active_func, ___unguarded_readlc_active_add_func | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
helpviewer_keywords:
- ___setlc_active_func
- ___unguarded_readlc_active_add_func
ms.assetid: 605ec4e3-81e5-4ece-935a-f434768cc702
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0a1ecc14403a7a08fed73fb10f15dd25051b0a28
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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