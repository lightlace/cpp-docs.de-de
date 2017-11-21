---
title: Length_is | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.length_is
dev_langs: C++
helpviewer_keywords: length_is attribute
ms.assetid: 1d99b883-84bb-4b1e-b098-eb780fc94f40
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6051502e81593bdb13f32d7904f912cc6f294cef
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="lengthis"></a>length_is
Gibt die Anzahl von Arrayelementen übermittelt werden sollen.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      [ length_is(  
   "expression"  
) ]  
```  
  
#### <a name="parameters"></a>Parameter  
 *Ausdruck*  
 Eine oder mehrere Programmiersprache C-Ausdrücke. Leere Argument Slots sind zulässig.  
  
## <a name="remarks"></a>Hinweise  
 Die **Length_is** C++-Attribut hat die gleiche Funktionalität wie die [Length_is](http://msdn.microsoft.com/library/windows/desktop/aa367068) MIDL-Attribut.  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [First_is](../windows/first-is.md) für ein Beispiel für einen Abschnitt eines Arrays angeben.  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|Im Feld `struct` oder **Union**, Parameter interface, Schnittstelle Methode|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keine|  
|**Ungültige Attribute**|Keine|  
  
 Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [TypeDef, Enum, Union- und Struct-Attribute](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Parameterattribute](../windows/parameter-attributes.md)   
 [first_is](../windows/first-is.md)   
 [max_is](../windows/max-is.md)   
 [last_is](../windows/last-is.md)   
 [size_is](../windows/size-is.md)   
