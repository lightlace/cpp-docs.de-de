---
title: _com_error::HRESULTToWCode | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_error::HRESULTToWCode
dev_langs: C++
helpviewer_keywords: HRESULTToWCode method [C++]
ms.assetid: ff3789f5-1047-41a0-b7e3-86dd8f638dba
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2dac335f3cc2ea26602a5f8a91a47db7d1ebe39b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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