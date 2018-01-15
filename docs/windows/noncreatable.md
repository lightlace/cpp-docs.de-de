---
title: Noncreatable | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.noncreatable
dev_langs: C++
helpviewer_keywords: noncreatable attribute
ms.assetid: 4d17937b-0bff-41af-ba57-53e18b7ab5a9
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bb9f67b4efac28a1cacd6301c8ca849246f9a481
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="noncreatable"></a>noncreatable
Definiert ein Objekt, das allein nicht instanziiert werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
[noncreatable]  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Die **Noncreatable** C++-Attribut hat die gleiche Funktionalität wie die [Noncreatable](http://msdn.microsoft.com/library/windows/desktop/aa367118) MIDL-Attribut und wird automatisch auf die generierten übergeben. IDL-Datei durch den Compiler.  
  
 Wenn dieses Attribut in einem Projekt, die ATL verwendet verwendet wird, ändert sich das Verhalten des Attributs. Zusätzlich zu den oben beschriebene Verhalten fügt das Attribut auch die [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) Makro. Dieses Makro zeigt ATL, dass das Objekt kann nicht extern erstellt werden.  
  
## <a name="example"></a>Beispiel  
  
```  
// cpp_attr_ref_noncreatable.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLib")];  
  
[object, uuid("11111111-1111-1111-1111-111111111111")]  
__interface A   
{  
};  
  
[coclass, uuid("11111111-1111-1111-1111-111111111112"), noncreatable]  
class CMyClass : public A   
{  
   HRESULT xx();  
};  
```  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**, `struct`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|**coclass**|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [Klassenattribute](../windows/class-attributes.md)   
