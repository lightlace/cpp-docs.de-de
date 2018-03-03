---
title: _com_error::WCodeToHRESULT | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_error::WCodeToHRESULT
dev_langs:
- C++
helpviewer_keywords:
- WCodeToHRESULT method [C++]
ms.assetid: 0ec43a4b-ca91-42d5-b270-3fde9c8412ea
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ca20bfa7574f604187734040b3ccc001d6aaf68d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="comerrorwcodetohresult"></a>_com_error::WCodeToHRESULT
**Microsoft-spezifisch**  
  
 Ordnet die 16-Bit- `wCode` auf 32-Bit- `HRESULT`.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      static HRESULT WCodeToHRESULT(  
   WORD wCode   
) throw( );  
```  
  
#### <a name="parameters"></a>Parameter  
 `wCode`  
 Der 16-Bit-`wCode`, der dem 32-Bit-`HRESULT` zugeordnet werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
 32-Bit-`HRESULT`, der vom 16-Bit- `wCode` zugeordnet wurde.  
  
## <a name="remarks"></a>Hinweise  
 Finden Sie unter der [WCode](../cpp/com-error-wcode.md) Memberfunktion.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_com_error:: wcode](../cpp/com-error-wcode.md)   
 [_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)   
 [_com_error-Klasse](../cpp/com-error-class.md)