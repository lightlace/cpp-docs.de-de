---
title: _com_error::errorInfo | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::ErrorInfo
dev_langs:
- C++
helpviewer_keywords:
- ErrorInfo method [C++]
ms.assetid: 071b446c-4395-4fb8-bd3d-300a8b25f5cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8fbc735dfae1b30209eccfd14f1170826fb07680
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
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