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
ms.openlocfilehash: ad1fb4dd281918b0d9ab3494c9a9f060468fc389
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40018096"
---
# <a name="local-c"></a>local (C++)
Wenn in der Kopfzeile der Schnittstelle verwendet wird, können Sie Sie den MIDL-Compiler als ein Header-Generator zu verwenden. Bei Verwendung in einer einzelnen Funktion kennzeichnet eine lokale Prozedur, die für die keine Stubs generiert werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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