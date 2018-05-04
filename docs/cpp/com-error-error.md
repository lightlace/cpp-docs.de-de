---
title: _com_error::Error | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::Error
- Error
dev_langs:
- C++
helpviewer_keywords:
- Error method [C++]
ms.assetid: b53a15fd-198e-4276-afcd-13439c4807f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 02afac78de5eb5908d477f8503ceeebffe46f672
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
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