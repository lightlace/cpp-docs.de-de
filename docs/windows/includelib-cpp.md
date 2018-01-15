---
title: Includelib (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.includelib
dev_langs: C++
helpviewer_keywords: includelib attribute
ms.assetid: cd90ea6e-5ae8-4f11-b8d1-662db95412b2
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: df6c38889db24cc1b4f28ce0bfe4cf96eb6b03a2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
 [einschließen](../windows/include-cpp.md)   
 [importlib](../windows/importlib.md)   
