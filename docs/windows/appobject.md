---
title: Appobject | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.appobject
dev_langs:
- C++
helpviewer_keywords:
- appobject attribute
ms.assetid: 8ce30b73-e945-403e-a755-6bc78078a695
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: aca26e156bbb6a883ed6d55a6a01da128982c127
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33856972"
---
# <a name="appobject"></a>appobject
Identifiziert die Co-Klasse als ein Anwendungsobjekt, die mit einer vollständigen .exe-Anwendung verknüpft ist, und gibt an, dass die Funktionen und Eigenschaften der Co-Klasse in diesem global verfügbar sind [Typbibliothek](../mfc/automation-clients-using-type-libraries.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
  
[appobject]  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Die **Appobject** C++-Attribut hat die gleiche Funktionalität wie die [Appobject](http://msdn.microsoft.com/library/windows/desktop/aa366726) MIDL-Attribut.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt eine einfache Klassendefinition ein Attributblock, die enthält vorangestellt **Appobject**:  
  
```  
// cpp_attr_ref_appobject.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="MyLib", uuid="f1ce17f0-a5df-4d26-95f6-0a122197ac5b")];  
  
[object, uuid="905de6db-7a12-45ab-9f8b-b39f5112f010"]  
__interface ICustom {};  
  
[coclass, appobject,uuid="00395340-745f-4b69-bd58-e2921452b9fc"]  
class A : public ICustom {  
   int i;  
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
 [typedef-, enum-, union- und struct-Attribute](../windows/typedef-enum-union-and-struct-attributes.md)   
