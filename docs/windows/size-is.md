---
title: Size_is | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.size_is
dev_langs: C++
helpviewer_keywords: size_is attribute
ms.assetid: 70192d09-f6c5-4d52-b3fe-303f8cb10aa5
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0e8b3f6e8df8ff7f493c50f52e1e839f4ca9baa9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="sizeis"></a>size_is
Geben Sie die Größe des Arbeitsspeichers für Größe Zeiger belegt, Größe von Zeigern auf großen Zeiger und Einzel- oder mehrdimensionale Arrays.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      [ size_is(  
   "expression"  
) ]  
```  
  
#### <a name="parameters"></a>Parameter  
 *Ausdruck*  
 Die Größe des Arbeitsspeichers für die Größe von Zeigern.  
  
## <a name="remarks"></a>Hinweise  
 Die **Size_is** C++-Attribut hat die gleiche Funktionalität wie die [Size_is](http://msdn.microsoft.com/library/windows/desktop/aa367164) MIDL-Attribut.  
  
## <a name="example"></a>Beispiel  
 Siehe das Beispiel für [First_is](../windows/first-is.md) für ein Beispiel für einen Abschnitt eines Arrays angeben.  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|Im Feld `struct` oder **Union**, Parameter interface, Schnittstelle Methode|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keine|  
|**Ungültige Attribute**|**max_is**|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [TypeDef, Enum, Union- und Struct-Attribute](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Parameterattribute](../windows/parameter-attributes.md)   
 [first_is](../windows/first-is.md)   
 [last_is](../windows/last-is.md)   
 [max_is](../windows/max-is.md)   
 [length_is](../windows/length-is.md)   
