---
title: Objekt (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.object
dev_langs: C++
helpviewer_keywords: object attribute
ms.assetid: f2d3c231-630d-4b4c-bd15-b1c30df362dd
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 75694398f01cdf790b292d53aff5466b1e27a919
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="object-c"></a>object (C++)
Identifiziert eine benutzerdefinierte Schnittstelle an.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
[object]  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Wenn vor der Schnittstellendefinition einer, die **Objekt** C++-Attribut bewirkt, dass die Schnittstelle in der IDL-Datei als eine benutzerdefinierte Schnittstelle abgelegt werden soll.  
  
 Alle mit Objekt markierte Schnittstelle erben muss **IUnknown**. Diese Bedingung erfüllt wird, wenn einer der Basisschnittstellen erben **IUnknown**. Wenn keine Basisschnittstellen erben **IUnknown**, der Compiler führt dazu, dass die Schnittstelle, die mit markierten **Objekt** Ableitung **IUnknown**.  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [Nonbrowsable](../windows/nonbrowsable.md) ein Beispiel zum Verwenden von **Objekt**.  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|`interface`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keine|  
|**Ungültige Attribute**|Keine|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [Schnittstellenattribut](../windows/interface-attributes.md)   
 [Duale](../windows/dual.md)   
 [Disp-Schnittstelle](../windows/dispinterface.md)   
 [benutzerdefinierte](../windows/custom-cpp.md)   
 [__interface](../cpp/interface.md)   
