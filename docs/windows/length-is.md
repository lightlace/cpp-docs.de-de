---
title: Length_is | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.length_is
dev_langs:
- C++
helpviewer_keywords:
- length_is attribute
ms.assetid: 1d99b883-84bb-4b1e-b098-eb780fc94f40
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d30a467bd929c68c35e06861087ec7f47d1f2d51
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40011906"
---
# <a name="lengthis"></a>length_is
Gibt die Anzahl von Elementen übertragen werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
[ length_is(  
   "expression"  
) ]  
```  
  
### <a name="parameters"></a>Parameter  
 *Ausdruck*  
 Eine oder mehrere Programmiersprache C-Ausdrücke. Leere Argumentliste Slots sind zulässig.  
  
## <a name="remarks"></a>Hinweise  
 Die **Length_is** C++-Attribut hat die gleiche Funktionalität wie die [Length_is](http://msdn.microsoft.com/library/windows/desktop/aa367068) MIDL-Attribut.  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [First_is](../windows/first-is.md) ein Beispiel für einen Abschnitt eines Arrays angeben.  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|Im Feld **Struktur** oder **Union**, Schnittstellenparameter,-Schnittstellenmethode|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [TypeDef, Enum, Union- und Struct-Attribute](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Parameterattribute](../windows/parameter-attributes.md)   
 [first_is](../windows/first-is.md)   
 [max_is](../windows/max-is.md)   
 [last_is](../windows/last-is.md)   
 [size_is](../windows/size-is.md)   