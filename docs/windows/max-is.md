---
title: Max_is | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.max_is
dev_langs:
- C++
helpviewer_keywords:
- max_is attribute
ms.assetid: 7c851f5c-6649-4d77-a792-247c37d8f560
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2799039aa2c198bcea3784876d8299fcaec59b20
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40012448"
---
# <a name="maxis"></a>max_is
Legt fest, den maximalen Wert für ein gültiges Array-Index.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
[ max_is(  
   "expression"  
) ]  
```  
  
### <a name="parameters"></a>Parameter  
 *Ausdruck*  
 Eine oder mehrere Programmiersprache C-Ausdrücke. Leere Argumentliste Slots sind zulässig.  
  
## <a name="remarks"></a>Hinweise  
 Die **Max_is** C++-Attribut hat die gleiche Funktionalität wie die [Max_is](http://msdn.microsoft.com/library/windows/desktop/aa367074) MIDL-Attribut.  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|Im Feld **Struktur** oder **Union**, Schnittstellenparameter,-Schnittstellenmethode|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|**size_is**|  
  
 Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [First_is](../windows/first-is.md) ein Beispiel für einen Abschnitt eines Arrays angeben.  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [TypeDef, Enum, Union- und Struct-Attribute](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Parameterattribute](../windows/parameter-attributes.md)   
 [first_is](../windows/first-is.md)   
 [last_is](../windows/last-is.md)   
 [length_is](../windows/length-is.md)   
 [size_is](../windows/size-is.md)   