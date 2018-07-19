---
title: _com_error::Error | Microsoft-Dokumentation
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
ms.openlocfilehash: 21f2da8c10b9b796740144f81d0390f1af124cab
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37942054"
---
# <a name="comerrorerror"></a>_com_error::Error
**Microsoft-spezifisch**  
  
 Ruft den HRESULT-Wert an den Konstruktor übergeben.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
HRESULT Error( ) const throw( );  
  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Unformatierte HRESULT-Elemente, die an den Konstruktor übergeben werden.  
  
## <a name="remarks"></a>Hinweise  
 Ruft das gekapselte HRESULT-Element in einem `_com_error` Objekt.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_com_error-Klasse](../cpp/com-error-class.md)