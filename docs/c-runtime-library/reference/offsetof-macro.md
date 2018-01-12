---
title: offsetof-Makro | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
f1_keywords: offsetof
dev_langs: C++
helpviewer_keywords:
- structure members, offset
- offsetof macro
ms.assetid: f3b4eb16-a882-4d38-afc9-eebd976a7352
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d99947615f2f24116f3d9b64e94daba60c848ec4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="offsetof-macro"></a>offsetof-Makro
Ruft den Offset eines Elements vom Anfang seiner übergeordneten Struktur ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      size_t offsetof(  
   structName,  
   memberName   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 *structName*  
 Der Name der übergeordneten Datenstruktur.  
  
 `memberName`  
 Der Name des Elements in der übergeordneten Datenstruktur, für das der Offset bestimmt werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
 `offsetof` gibt den Offset des angegebenen Elements vom Anfang seiner übergeordneten Datenstruktur in Bytes zurück. Ist für Bitfelder nicht definiert.  
  
## <a name="remarks"></a>Hinweise  
 Das `offsetof`-Makro gibt den Offset von `memberName` vom Strukturanfang, der von *structName* als ein Wert vom Typ `size_t` festgelegt ist, in Bytes zurück. Sie können Typen mit dem `struct`-Schlüsselwort angeben.  
  
> [!NOTE]
>  `offsetof` ist keine Funktion und kann nicht mit einem C-Prototyp beschrieben werden.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`offsetof`|\<stddef.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Speicherbelegung](../../c-runtime-library/memory-allocation.md)