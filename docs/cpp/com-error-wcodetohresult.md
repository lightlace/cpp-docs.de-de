---
title: _com_error::WCodeToHRESULT | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::WCodeToHRESULT
dev_langs:
- C++
helpviewer_keywords:
- WCodeToHRESULT method [C++]
ms.assetid: 0ec43a4b-ca91-42d5-b270-3fde9c8412ea
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dce98775007360e3fdd4177141f7a550548d3679
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939194"
---
# <a name="comerrorwcodetohresult"></a>_com_error::WCodeToHRESULT
**Microsoft-spezifisch**  
  
 Ordnet die 16-Bit- *wCode* in 32-Bit-HRESULT.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      static HRESULT WCodeToHRESULT(  
   WORD wCode   
) throw( );  
```  
  
#### <a name="parameters"></a>Parameter  
 *WCode*  
 Die 16-Bit- *wCode* , 32-Bit-HRESULT zugeordnet werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
 zugeordnet aus dem 16-Bit-32-Bit-HRESULT *wCode*.  
  
## <a name="remarks"></a>Hinweise  
 Finden Sie unter den [WCode](../cpp/com-error-wcode.md) Member-Funktion.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_com_error:: wcode](../cpp/com-error-wcode.md)   
 [_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)   
 [_com_error-Klasse](../cpp/com-error-class.md)