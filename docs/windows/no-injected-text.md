---
title: No_injected_text | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.no_injected_text
dev_langs:
- C++
helpviewer_keywords:
- no_injected_text attribute
ms.assetid: 5256f808-e41e-4f4a-9ea5-e447919f5696
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 74336ffaa5e1f9f1990acedf1669526c9152b82b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="noinjectedtext"></a>no_injected_text
Verhindert, dass den Compiler Code aufgrund der Verwendung des Attributs injiziert.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      [ no_injected_text(  
   boolean  
) ];  
```  
  
#### <a name="parameters"></a>Parameter  
 `boolean`(optional)  
 **"true"** ggf. keinen Code eingeschleust, **"false"** damit Code eingefügt werden kann. **"true"** ist die Standardeinstellung.  
  
## <a name="remarks"></a>Hinweise  
 Die häufigste Verwendung von der **No_injected_text** C++-Attribut wird durch die [/FX](../build/reference/fx-merge-injected-code.md) -Compileroption fügt die **No_injected_text** Attribut in der MRG-Datei.  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|Überall|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Compilerattribute](../windows/compiler-attributes.md)   
