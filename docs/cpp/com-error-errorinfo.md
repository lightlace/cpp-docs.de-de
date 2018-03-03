---
title: _com_error::errorInfo | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_error::ErrorInfo
dev_langs:
- C++
helpviewer_keywords:
- ErrorInfo method [C++]
ms.assetid: 071b446c-4395-4fb8-bd3d-300a8b25f5cd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 642078d84f72a553e9b2407b279265a3a7e77522
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="comerrorerrorinfo"></a>_com_error::ErrorInfo
**Microsoft-spezifisch**  
  
 Ruft die **IErrorInfo** Objekt an den Konstruktor übergeben.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
IErrorInfo * ErrorInfo( ) const throw( );  
  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Unformatierte **IErrorInfo** Element an den Konstruktor übergeben.  
  
## <a name="remarks"></a>Hinweise  
 Ruft das gekapselte **IErrorInfo** Element in einem `_com_error` -Objekt, oder **NULL** kein **IErrorInfo** -Element erfasst ist. Der Aufrufer muss Aufrufen **Version** Verwendung für das zurückgegebene Objekt abgeschlossen.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_com_error-Klasse](../cpp/com-error-class.md)