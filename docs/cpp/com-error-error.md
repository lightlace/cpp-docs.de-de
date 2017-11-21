---
title: _com_error::Error | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_error::Error
- Error
dev_langs: C++
helpviewer_keywords: Error method [C++]
ms.assetid: b53a15fd-198e-4276-afcd-13439c4807f7
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 010d1b2e10d1435855c35929516ff0e7f3fd8d4e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="comerrorerror"></a>_com_error::Error
**Microsoft-spezifisch**  
  
 Ruft das an den Konstruktor übergebene `HRESULT` ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
HRESULT Error( ) const throw( );  
  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Unformatiertes `HRESULT`-Element, das an den Konstruktor übergeben wird.  
  
## <a name="remarks"></a>Hinweise  
 Ruft das gekapselte `HRESULT`-Element in einem `_com_error`-Objekt ab.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_com_error-Klasse](../cpp/com-error-class.md)