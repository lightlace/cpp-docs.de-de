---
title: lokale (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.local
dev_langs:
- C++
helpviewer_keywords:
- local attribute
ms.assetid: 35cdd668-bd8e-492a-b7b8-263e7b662437
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 17a57ad56402b345aa64e4e4fd02bc57dd7f0321
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33877916"
---
# <a name="local-c"></a>local (C++)
Bei Verwendung in der Schnittstelle Header können Sie die MIDL-Compiler als ein Header-Generator zu verwenden. Wenn in einer einzelnen Funktion verwendet wird, kennzeichnet eine lokale Prozedur für die keine Stubs generiert werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
[local]  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Die `local` C++-Attribut hat die gleiche Funktionalität wie die [lokale](http://msdn.microsoft.com/library/windows/desktop/aa367071) MIDL-Attribut.  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [Aufruf als](../windows/call-as.md) ein Beispiel zum Verwenden von `local`.  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|`interface`,-Schnittstellenmethode|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|**dispinterface**|  
  
 Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [Schnittstellenattribut](../windows/interface-attributes.md)   
 [Methodenattribut](../windows/method-attributes.md)   
 [call_as](../windows/call-as.md)   
