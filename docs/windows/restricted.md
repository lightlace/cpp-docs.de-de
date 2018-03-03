---
title: "Eingeschränkte | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.restricted
dev_langs:
- C++
helpviewer_keywords:
- restricted attribute
ms.assetid: 504a96be-b904-4269-8be1-920feba201b4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 569d57da691f40857f54dcae1c383ff7758564f4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="restricted"></a>restricted
Gibt an, dass ein Mitglied aus einem Modul, Schnittstelle oder Disp-Schnittstelle kann nicht nach dem Zufallsprinzip aufgerufen werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      [ restricted(  
   interfaces  
) ]  
```  
  
#### <a name="parameters"></a>Parameter  
 `interfaces`  
 Eine oder mehrere Schnittstellen, die nach dem Zufallsprinzip nicht auf ein COM-Objekt aufgerufen werden können. Dieser Parameter ist nur gültig, wenn auf eine Klasse angewendet werden.  
  
## <a name="remarks"></a>Hinweise  
 Die **eingeschränkte** C++-Attribut hat die gleiche Funktionalität wie die [eingeschränkte](http://msdn.microsoft.com/library/windows/desktop/aa367157) MIDL-Attribut.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt, wie Sie die **eingeschränkte** Attribut:  
  
```  
// cpp_attr_ref_restricted.cpp  
// compile with: /LD  
#include "windows.h"  
#include "unknwn.h"  
[module(name="MyLib")];  
  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface a  
{  
};  
  
[object, uuid("00000000-0000-0000-0000-000000000002")]  
__interface b  
{  
};  
  
[coclass, restricted(a,b), uuid("00000000-0000-0000-0000-000000000003")]  
class c : public a, public b  
{  
};  
```  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|-Schnittstellenmethode, `interface`, **Klasse**,`struct`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|**coclass** (bei Anwendung auf **class** oder `struct`)|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [Schnittstellenattribut](../windows/interface-attributes.md)   
 [Methodenattribut](../windows/method-attributes.md)   
