---
title: Duale | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.dual
dev_langs:
- C++
helpviewer_keywords:
- dual attribute
ms.assetid: 5d4a9069-d819-42cd-ba56-bbcda17157d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 460e3f5316bc4b4509e563fda2354106164b3b1a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33872379"
---
# <a name="dual"></a>dual
Fügt eine Schnittstelle in der IDL-Datei als eine duale Schnittstelle.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
[dual]  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Wenn die **duale** C++-Attribut vorangestellt ist, eine Schnittstelle, die er bewirkt, dass die Schnittstelle in der bibliotheksblock in der generierten IDL-Datei abgelegt werden soll.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code ist ein Attributblock, die verwendet **duale** vor einer Schnittstellendefinition:  
  
```  
// cpp_attr_ref_dual.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="MyLibrary")];  
  
[uuid("2F5F63F1-16DA-11d2-9E7B-00C04FB926DA"), dual]  
  
__interface IStatic : IDispatch   
{  
   HRESULT Func1(int i);  
   [   propget,   
      id(1),   
      bindable,   
      displaybind,   
      defaultbind,   
      requestedit  
   ]   
   HRESULT P1([out, retval] long *nSize);  
   [   propput,   
      id(1),   
      bindable,   
      displaybind,   
      defaultbind,   
      requestedit  
   ]   
   HRESULT P1([in] long nSize);      
};  
  
[cpp_quote("#include file.h")];  
```  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|`interface`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|**dispinterface**|  
  
 Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [Attribute nach Verwendung](../windows/attributes-by-usage.md)   
 [Benutzerdefinierte](../windows/custom-cpp.md)   
 [Disp-Schnittstelle](../windows/dispinterface.md)   
 [Objekt](../windows/object-cpp.md)   
 [__interface](../cpp/interface.md)   
