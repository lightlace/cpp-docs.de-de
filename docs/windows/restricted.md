---
title: Eingeschränkte | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.restricted
dev_langs:
- C++
helpviewer_keywords:
- restricted attribute
ms.assetid: 504a96be-b904-4269-8be1-920feba201b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e1d688d4ebca5d2cc01901f5fe1afaa4536b71bb
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892877"
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
|**Betrifft**|-Schnittstellenmethode, `interface`, **Klasse**, `struct`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|**coclass** (bei Anwendung auf **class** oder `struct`)|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [Schnittstellenattribut](../windows/interface-attributes.md)   
 [Methodenattribut](../windows/method-attributes.md)   
