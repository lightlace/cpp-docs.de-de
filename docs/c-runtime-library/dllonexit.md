---
title: __dllonexit | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: __dllonexit
apilocation:
- msvcrt.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr80.dll
- msvcr120.dll
- msvcr90.dll
- msvcr120_clr0400.dll
apitype: DLLExport
f1_keywords: __dllonexit
dev_langs: C++
helpviewer_keywords: __dllonexit
ms.assetid: 708f2ceb-f95c-46b0-a58d-d68b3fa36f12
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7ed3b28381b92f4f11e4be99f97a2615a8379274
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="dllonexit"></a>__dllonexit
Registriert eine Routine, die zum Zeitpunkt der Beendigung aufgerufen werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
_onexit_t __dllonexit(   _onexit_t func,  
   _PVFV **  pbegin,   
   _PVFV **  pend   
   )  
```  
  
#### <a name="parameters"></a>Parameter  
 `func`  
 Ein Zeiger auf eine Funktion, die zum Zeitpunkt der Beendigung ausgeführt werden solle.  
  
 `pbegin`  
 Ein Zeiger auf eine Variable, die auf den Anfang einer Liste mit Funktionen zeigt, die beim Trennen ausgeführt werden sollen.  
  
 `pend`  
 Ein Zeiger auf eine Variable, die auf das Ende einer Liste mit Funktionen zeigt, die beim Trennen ausgeführt werden sollen.  
  
## <a name="return-value"></a>Rückgabewert  
 Bei Erfolg ein Zeiger auf die Funktion des Benutzers. Andernfalls ein NULL-Zeiger.  
  
## <a name="remarks"></a>Hinweise  
 Die `__dllonexit`-Funktion unterscheidet sich von der [_onexit](../c-runtime-library/reference/onexit-onexit-m.md)-Funktion insofern, als dass die von der Funktion verwendeten globalen Variablen für diese Routine nicht sichtbar sind. Anstelle von globalen Variablen werden von dieser Funktion die Parameter `pbegin` und `pend` verwendet.  
  
 Von den Funktionen `_onexit` und `atexit` in einer DLL, die mit MSVCRT.LIB verknüpft ist, müssen jeweils eigene atexit/_onexit-Listen verwaltet werden. Diese Routine ist der Worker, der von DLLs dieser Art aufgerufen wird.  
  
 Der Typ `_PVFV` ist als `typedef void (__cdecl *_PVFV)(void)` definiert.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderliche Datei|  
|-------------|-------------------|  
|__dllonexit|onexit.c|  
  
## <a name="see-also"></a>Siehe auch  
 [_onexit, _onexit_m](../c-runtime-library/reference/onexit-onexit-m.md)