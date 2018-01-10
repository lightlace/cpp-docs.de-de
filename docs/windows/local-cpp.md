---
title: lokale (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.local
dev_langs: C++
helpviewer_keywords: local attribute
ms.assetid: 35cdd668-bd8e-492a-b7b8-263e7b662437
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3543adfe0cb25f7946e6ed6c81c4bd66a7b60324
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
