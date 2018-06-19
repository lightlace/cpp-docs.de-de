---
title: nonextensible | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.nonextensible
dev_langs:
- C++
helpviewer_keywords:
- nonextensible attribute
ms.assetid: c7ef1554-809f-4ea0-a7cd-dc7786d40c3e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 87cdbf66676ed2a3e6054006270b39ad80325857
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33881600"
---
# <a name="nonextensible"></a>nonextensible
Gibt an, dass die `IDispatch` Implementierung enthält nur die Eigenschaften und Methoden aufgelistet, die in die schnittstellenbeschreibung und können nicht mit zusätzlichen Elementen zur Laufzeit erweitert werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
[nonextensible]  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Die **nonextensible** C++-Attribut hat die gleiche Funktionalität wie die [nonextensible](http://msdn.microsoft.com/library/windows/desktop/aa367120) MIDL-Attribut.  
  
 Verwenden von **nonextensible** erfordert außerdem die [Oleautomation](../windows/oleautomation.md) Attribut.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt eine Verwendung von der **nonextensible** Attribut:  
  
```  
// cpp_attr_ref_nonextensible.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="ATLFIRELib")];  
[export] typedef long HRESULT;  
  
[dual, nonextensible, ms_union, oleautomation,   
uuid("00000000-0000-0000-0000-000000000001")]  
__interface IFireTabCtrl  
{  
   HRESULT procedure (int i);   
};  
```  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|`interface`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|**Duale** und **Oleautomation**, oder **Disp-Schnittstelle**|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [Schnittstellenattribut](../windows/interface-attributes.md)   
