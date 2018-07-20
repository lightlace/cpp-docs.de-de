---
title: Includelib (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.includelib
dev_langs:
- C++
helpviewer_keywords:
- includelib attribute
ms.assetid: cd90ea6e-5ae8-4f11-b8d1-662db95412b2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 252a5d953dd05edc494daf8c4a45322d5511f979
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878891"
---
# <a name="includelib-c"></a>includelib (C++)
Bewirkt, dass eine IDL oder .h-Datei, in der generierten IDL-Datei eingeschlossen werden sollen.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      [ includelib(  
   name.idl  
) ];  
```  
  
#### <a name="parameters"></a>Parameter  
 *Name.idl*  
 Der Name der IDL-Datei, die als Teil der generierten IDL-Datei eingeschlossen werden sollen.  
  
## <a name="remarks"></a>Hinweise  
 Die `includelib` C++-Attribut bewirkt, dass eine IDL oder .h-Datei, in der generierten IDL-Datei eingeschlossen werden sollen, nachdem die `importlib` Anweisung.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code ist in einer CPP-Datei gezeigt:  
  
```  
// cpp_attr_ref_includelib.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[includelib("includelib.idl")];  
```  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|Überall|  
|**Wiederholbar**|Ja|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [Eigenständige Attribute](../windows/stand-alone-attributes.md)   
 [Importieren](../windows/import.md)   
 [importidl](../windows/importidl.md)   
 [Einschließen](../windows/include-cpp.md)   
 [importlib](../windows/importlib.md)   
