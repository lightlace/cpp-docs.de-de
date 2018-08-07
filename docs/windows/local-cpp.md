---
title: lokal (C++) | Microsoft-Dokumentation
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
ms.openlocfilehash: efa937c1eaabb23fe5a360444f8c2105b735b260
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2018
ms.locfileid: "39604199"
---
# <a name="local-c"></a>local (C++)
Wenn in der Kopfzeile der Schnittstelle verwendet wird, können Sie Sie den MIDL-Compiler als ein Header-Generator zu verwenden. Bei Verwendung in einer einzelnen Funktion kennzeichnet eine lokale Prozedur, die für die keine Stubs generiert werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
[local]  
```  
  
## <a name="remarks"></a>Hinweise  
 Die **lokalen** C++-Attribut hat die gleiche Funktionalität wie die [lokalen](http://msdn.microsoft.com/library/windows/desktop/aa367071) MIDL-Attribut.  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [Call_as](../windows/call-as.md) ein Beispiel zur Verwendung für **lokalen**.  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|**Schnittstelle**,-Schnittstellenmethode|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|`dispinterface`|  
  
 Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [Schnittstellenattribut](../windows/interface-attributes.md)   
 [Methodenattribute](../windows/method-attributes.md)   
 [call_as](../windows/call-as.md)   