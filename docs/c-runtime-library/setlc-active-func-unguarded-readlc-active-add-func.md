---
title: ___setlc_active_func, ___unguarded_readlc_active_add_func | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
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
dev_langs:
- C++
helpviewer_keywords:
- ___setlc_active_func
- ___unguarded_readlc_active_add_func
ms.assetid: 605ec4e3-81e5-4ece-935a-f434768cc702
caps.latest.revision: 5
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 08cda2e2b3f04663f3435ac9259117d54de80beb
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

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
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`___setlc_active_func`, `___unguarded_readlc_active_add_func`|Keine|  
  
## <a name="see-also"></a>Siehe auch  
 [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)
