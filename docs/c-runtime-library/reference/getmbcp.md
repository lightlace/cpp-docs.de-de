---
title: _getmbcp | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _getmbcp
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
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _getmbcp
- getmbcp
dev_langs:
- C++
helpviewer_keywords:
- code pages, determining current
- _getmbcp function
- getmbcp function
ms.assetid: 2db202d4-5c3d-4871-a0b8-ceb0b79ee7bb
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 4bc1000e9443d60e966ef6a929ed134acd44f1b7
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="getmbcp"></a>_getmbcp
Ruft die aktuelle Codepage ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
int _getmbcp( void );  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt die aktuelle Multibyte-Codepage zurück. Ein Rückgabewert von 0 gibt an, dass eine Einzelbyte-Codepage verwendet wird.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_getmbcp`|\<mbctype.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="see-also"></a>Siehe auch  
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)
