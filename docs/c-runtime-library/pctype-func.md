---
title: __pctype_func | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- __pctype_func
apilocation:
- msvcrt.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
- msvcr80.dll
apitype: DLLExport
f1_keywords:
- __pctype_func
dev_langs:
- C++
helpviewer_keywords:
- __pctype_func
ms.assetid: d52b8add-d07d-4516-a22f-e836cde0c57f
caps.latest.revision: 2
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 56370402ae31d3ea6f4897eb8a7068ed5e8f9bc4
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="pctypefunc"></a>__pctype_func
Ruft einen Zeiger auf ein Array an Zeichenklassifizierungsinformationen ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
const unsigned short *__pctype_func(  
   )  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein Array an Zeichenklassifizierungsinformationen.  
  
## <a name="remarks"></a>Hinweise  
 Die Informationen in der Zeichenklassifizierungstabelle sind nur zur internen Verwendung geeignet und werden von verschiedenen Funktionen verwendet, die Zeichen vom Typ `char` klassifizieren. Weitere Informationen finden Sie im `Remarks`-Abschnitt von [_pctype, _pwctype, _wctype, _mbctype, _mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|__pctype_func|ctype.h|  
  
## <a name="see-also"></a>Siehe auch  
 [_pctype, _pwctype, _wctype, _mbctype, _mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md)
