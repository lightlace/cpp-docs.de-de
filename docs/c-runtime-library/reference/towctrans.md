---
title: towctrans | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- towctrans
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- towctrans
dev_langs:
- C++
helpviewer_keywords:
- towctrans function
ms.assetid: 1ed1e70d-7b31-490f-a7d9-42564b5924ca
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: fcd97b3af0bb7e469db18b1a7ff8290af5df1bc4
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="towctrans"></a>towctrans
Transformiert ein Zeichen.  
  
## <a name="syntax"></a>Syntax  
  
```  
wint_t towctrans(  
   wint_t c,  
   wctrans_t category   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `c`  
 Das Zeichen, das Sie transformieren möchten.  
  
 `category`  
 Ein Bezeichner, der den Rückgabewert von [wctrans](../../c-runtime-library/reference/wctrans.md) enthält.  
  
## <a name="return-value"></a>Rückgabewert  
 Das Zeichen `c`, nachdem `towctrans` die Transformationsregel in `category` angewendet hat.  
  
## <a name="remarks"></a>Hinweise  
 Der Wert von `category` muss zuvor bei einem erfolgreichen Aufruf von [wctrans](../../c-runtime-library/reference/wctrans.md) zurückgegeben worden sein.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`towctrans`|\<wctype.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
 Unter `wctrans` finden Sie ein Beispiel mit `towctrans`.  
  
## <a name="see-also"></a>Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)
