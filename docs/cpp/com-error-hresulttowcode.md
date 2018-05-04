---
title: _com_error::HRESULTToWCode | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::HRESULTToWCode
dev_langs:
- C++
helpviewer_keywords:
- HRESULTToWCode method [C++]
ms.assetid: ff3789f5-1047-41a0-b7e3-86dd8f638dba
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7e3955fcda665e08e5415652a1e8f1f232d0fe13
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="comerrorhresulttowcode"></a>_com_error::HRESULTToWCode
**Microsoft-spezifisch**  
  
 Ordnet 32-Bit-`HRESULT` dem 16-Bit-`wCode` zu.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      static WORD HRESULTToWCode(  
   HRESULT hr   
) throw( );  
```  
  
#### <a name="parameters"></a>Parameter  
 `hr`  
 Die 32-Bit- `HRESULT` 16-Bit zugeordnet werden `wCode`.  
  
## <a name="return-value"></a>Rückgabewert  
 16-Bit- `wCode` zugeordnet, die von der 32-Bit- `HRESULT`.  
  
## <a name="remarks"></a>Hinweise  
 Finden Sie unter [_com_error:: wcode](../cpp/com-error-wcode.md) für Weitere Informationen.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_com_error:: wcode](../cpp/com-error-wcode.md)   
 [_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)   
 [_com_error-Klasse](../cpp/com-error-class.md)