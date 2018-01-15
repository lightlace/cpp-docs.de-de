---
title: Helpstring | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.helpstring
dev_langs: C++
helpviewer_keywords: helpstring attribute [C++]
ms.assetid: 0401e905-a63e-4fad-98d0-d1efea111966
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f3df545f5d87d36c26d999dc3a5fbee8720830c6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="helpstring"></a>helpstring
Gibt eine Zeichenfolge, die verwendet wird, um das Element zu beschreiben, auf dem es angewendet.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      [ helpstring(  
   "string"  
) ]  
```  
  
#### <a name="parameters"></a>Parameter  
 `string`  
 Der Text, der den Hilfetext.  
  
## <a name="remarks"></a>Hinweise  
 Die **Helpstring** C++-Attribut hat die gleiche Funktionalität wie die [Helpstring](http://msdn.microsoft.com/library/windows/desktop/aa366856) MIDL-Attribut.  
  
## <a name="example"></a>Beispiel  
 Siehe das Beispiel für ["DefaultValue"](../windows/defaultvalue.md) ein Beispiel zum Verwenden von **Helpstring**.  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|`interface`, `typedef`, **Klasse**, Methode, Eigenschaft|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [Schnittstellenattribut](../windows/interface-attributes.md)   
 [Klassenattribute](../windows/class-attributes.md)   
 [Methodenattribut](../windows/method-attributes.md)   
 [TypeDef, Enum, Union- und Struct-Attribute](../windows/typedef-enum-union-and-struct-attributes.md)   
 [HelpFile](../windows/helpfile.md)   
 [helpcontext](../windows/helpcontext.md)   
