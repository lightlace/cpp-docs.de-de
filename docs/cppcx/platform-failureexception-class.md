---
title: 'Platform:: FailureException-Klasse | Microsoft Docs'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::FailureException::FailureException
- VCCORLIB/Platform::FailureException
dev_langs:
- C++
helpviewer_keywords:
- Platform::FailureException
ms.assetid: 1729cd07-bfc2-448e-9db5-185d5cbf5b81
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1094810663ce0a0abf8234af386d7a8427472ced
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33088140"
---
# <a name="platformfailureexception-class"></a>Platform::FailureException-Klasse
Wird ausgelöst, wenn bei dem Vorgang ein Fehler aufgetreten ist. Dies entspricht dem E_FAIL HRESULT.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
public ref class FailureException : COMException,    IException,    IPrintable,    IEquatable  
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter der [COMException](../cppcx/platform-comexception-class.md) -Klasse.  
  
### <a name="requirements"></a>Anforderungen  
 **Unterstützter Client:** Windows 8  
  
 **Unterstützter Server:** Windows Server 2012  
  
 **Namespace:** Platform  
  
 **Metadaten:** platform.winmd  
  
## <a name="see-also"></a>Siehe auch  
 [Platform::COMException-Klasse](../cppcx/platform-comexception-class.md)