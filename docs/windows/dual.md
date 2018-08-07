---
title: Duale | Microsoft-Dokumentation
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
ms.openlocfilehash: b52359d1f50f5ea3bad4075432fd8ae0e468d2df
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39571017"
---
# <a name="dual"></a>dual
Fügt eine Schnittstelle in der IDL-Datei als eine duale Schnittstelle an.  
  
## <a name="syntax"></a>Syntax  
  
```  
[dual]  
```  
  
## <a name="remarks"></a>Hinweise  
 Wenn die **dual** C++-Attribut einer Schnittstelle vorangeht, wird die Schnittstelle, in den bibliotheksblock in der generierten IDL-Datei platziert werden soll.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code ist ein Attributblock, die verwendet **dual** vor einer Schnittstellendefinition:  
  
```cpp  
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
|**Betrifft**|**interface**|  
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