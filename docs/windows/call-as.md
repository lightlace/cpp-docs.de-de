---
title: Aufruf als | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.call_as
dev_langs:
- C++
helpviewer_keywords:
- call_as attribute
ms.assetid: a09d7f1f-353b-4870-9b45-f0284161695d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 68707ea7e00665d12165c7838b1a2ad3440f944d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="callas"></a>call_as
Ermöglicht eine [lokale](../windows/local-cpp.md) Funktion, um eine remote-Funktion zugeordnet werden, wenn die remote-Funktion aufgerufen wird, die lokale Funktion aufgerufen wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      [ call_as(  
   function  
) ]  
```  
  
#### <a name="parameters"></a>Parameter  
 *function*  
 Die lokale-Funktion, die Sie aufgerufen werden, wenn eine remote-Funktion aufgerufen wird.  
  
## <a name="remarks"></a>Hinweise  
 Die **Aufruf als** C++-Attribut hat die gleiche Funktionalität wie die [Aufruf als](http://msdn.microsoft.com/library/windows/desktop/aa366748) MIDL-Attribut.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt, wie Sie verwenden können **Aufruf als** zuordnen eine Funktion nicht remotefähig (**f1**) an eine remotefähige-Funktion (**Remf1**):  
  
```  
// cpp_attr_ref_call_as.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="MyLib")];  
[dual, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IMInterface {  
   [local] HRESULT f1 ( int i );  
   [call_as(f1)] HRESULT Remf1 ( int i );   
};  
```  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|Schnittstellenmethode|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [Methodenattribut](../windows/method-attributes.md)   
 [local](../windows/local-cpp.md)   
