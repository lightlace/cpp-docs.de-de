---
title: _com_error::HRESULTToWCode | Microsoft-Dokumentation
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
ms.openlocfilehash: f0ddac28c4f39cdf11abbdf38c3af5d00c22413a
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39401905"
---
# <a name="comerrorhresulttowcode"></a>_com_error::HRESULTToWCode
**Microsoft-spezifisch**  
  
 Ordnet 32-Bit-HRESULT 16-Bit- `wCode`.  
  
## <a name="syntax"></a>Syntax  
  
```  
static WORD HRESULTToWCode(  
   HRESULT hr   
) throw( );  
```  
  
#### <a name="parameters"></a>Parameter  
 *HR*  
 Die 32-Bit-HRESULT in 16-Bit zugeordnet werden `wCode`.  
  
## <a name="return-value"></a>Rückgabewert  
 16-Bit- `wCode` von 32-Bit-HRESULT zugeordnet.  
  
## <a name="remarks"></a>Hinweise  
 Finden Sie unter [_com_error:: wcode](../cpp/com-error-wcode.md) für Weitere Informationen.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_com_error:: wcode](../cpp/com-error-wcode.md)   
 [_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)   
 [_com_error-Klasse](../cpp/com-error-class.md)