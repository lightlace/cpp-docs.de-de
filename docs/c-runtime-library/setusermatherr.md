---
title: __setusermatherr | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- __setusermatherr
apilocation:
- msvcr80.dll
- msvcr90.dll
- msvcrt.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr100.dll
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- __setusermatherr
dev_langs:
- C++
helpviewer_keywords:
- __setusermatherr
ms.assetid: f306818d-381a-4d68-8739-71b92bacb5ea
caps.latest.revision: 2
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 43b4b5ec6cddcb4a325201a4f9e2afe02ef9454a
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="setusermatherr"></a>__setusermatherr
Gibt eine benutzerdefinierte Routine an, die anstelle der [_matherr](../c-runtime-library/reference/matherr.md)-Routine verwendet wird, um Mathematikfehler zu behandeln.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
void __setusermatherr(  
   _HANDLE_MATH_ERROR pf   
   )  
```  
  
#### <a name="parameters"></a>Parameter  
 `pf`  
 Zeiger zu einer Implementierung von `_matherr`, die vom Benutzer bereitgestellt wird.  
  
 Der Typ des `pf`-Parameters ist als `typedef int (__cdecl * _HANDLE_MATH_ERROR)(struct _exception *)` deklariert.  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|__setusermatherr|matherr.c|
