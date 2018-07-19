---
title: Last_is | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.last_is
dev_langs:
- C++
helpviewer_keywords:
- last_is attribute
ms.assetid: 9e045ac0-fa38-4249-af55-67bde5d0a58c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f27c0a12ddf5fe87f7065a16d042bd0afcfc0315
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33877520"
---
# <a name="lastis"></a>last_is
Gibt den Index des letzten Arrayelements übermittelt werden sollen.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      [ last_is(  
   "expression"  
) ]  
```  
  
#### <a name="parameters"></a>Parameter  
 *Ausdruck*  
 Eine oder mehrere Programmiersprache C-Ausdrücke. Leere Argument Slots sind zulässig.  
  
## <a name="remarks"></a>Hinweise  
 Die **Last_is** C++-Attribut hat die gleiche Funktionalität wie die [Last_is](http://msdn.microsoft.com/library/windows/desktop/aa367066) MIDL-Attribut.  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [First_is](../windows/first-is.md) für ein Beispiel für einen Abschnitt eines Arrays angeben.  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|Im Feld `struct` oder **Union**, Parameter interface, Schnittstelle Methode|  
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
 [length_is](../windows/length-is.md)   
 [size_is](../windows/size-is.md)   
