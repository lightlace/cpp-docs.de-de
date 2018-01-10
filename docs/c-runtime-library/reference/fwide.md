---
title: fwide | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: fwide
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
f1_keywords: fwide
dev_langs: C++
helpviewer_keywords: fwide function
ms.assetid: a4641f5b-d74f-4946-95d5-53a64610d28d
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 79f972385f51bdf9fa04a1c368a991591659a7f2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="fwide"></a>fwide
Nicht implementiert  
  
## <a name="syntax"></a>Syntax  
  
```  
int fwide(  
   FILE *stream,  
   int mode;  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `stream`  
 Zeiger auf die `FILE`-Struktur (ignoriert).  
  
 `mode`  
 Die neue Breite des Streams: positiv für Breitzeichen, negativ für Bytes, null, um unverändert zu lassen. (Dieser Wert wird ignoriert.)  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Funktion gibt zurzeit nur `mode` zurück.  
  
## <a name="remarks"></a>Hinweise  
 Die aktuelle Version dieser Funktion stimmt nicht mit dem Standard überein.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------|  
|`fwide`|\<wchar.h>|  
  
 Weitere Informationen finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).