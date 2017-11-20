---
title: 'Platform:: FailureException-Klasse | Microsoft Docs'
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- VCCORLIB/Platform::FailureException::FailureException
- VCCORLIB/Platform::FailureException
dev_langs: C++
helpviewer_keywords: Platform::FailureException
ms.assetid: 1729cd07-bfc2-448e-9db5-185d5cbf5b81
caps.latest.revision: "3"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 441c8893015bb2f2a961c83b129af8f03dd527df
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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