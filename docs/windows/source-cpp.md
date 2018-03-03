---
title: Quelle (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.source
dev_langs:
- C++
helpviewer_keywords:
- source attribute
ms.assetid: 1878d05d-7709-4e97-b114-c62f38f5140e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f4bfc79a76ece278c62b4895cdeb2e10d6df42aa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="source-c"></a>source (C++)
Für eine Klasse gibt Schnittstellen für Verbindungspunkte der COM-Objekt. Auf eine Eigenschaft oder Methode gibt Sie an, dass das Element zurückgibt, ein Objekt oder eine Variante, die Quelle von Ereignissen ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      [ source(  
   interfaces  
) ]  
```  
  
#### <a name="parameters"></a>Parameter  
 `interfaces`  
 Eine oder mehrere Schnittstellen, die Sie angeben, wenn Sie die Quelle anwenden Attribut auf eine Klasse. Dieser Parameter wird nicht verwendet werden, wenn die Quelle auf eine Eigenschaft oder Methode angewendet wird.  
  
## <a name="remarks"></a>Hinweise  
 Die **Quelle** C++-Attribut hat die gleiche Funktionalität wie die [Quelle](http://msdn.microsoft.com/library/windows/desktop/aa367166) MIDL-Attribut.  
  
 Sie können der [Standard](../windows/default-cpp.md) Attribut, um die Standard-Quellschnittstelle für ein Objekt anzugeben.  
  
## <a name="example"></a>Beispiel  
  
```  
// cpp_attr_ref_source.cpp  
// compile with: /LD  
#include "windows.h"  
#include "unknwn.h"  
[module(name="MyLib")];  
  
[object, uuid(11111111-1111-1111-1111-111111111111)]  
__interface b  
{  
   [id(0), propget, bindable, displaybind, defaultbind, requestedit]  
   HRESULT get_I([out, retval]long *i);  
};  
  
[object, uuid(11111111-1111-1111-1111-111111111131)]  
__interface c  
{  
   [id(0), propget, bindable, displaybind, defaultbind, requestedit]   
   HRESULT et_I([out, retval]long *i);  
};  
  
[coclass, default(c), uuid(11111111-1111-1111-1111-111111111132)]  
class N : public b  
{  
};  
  
[coclass, source(c), default(b, c), uuid(11111111-1111-1111-1111-111111111133)]  
class NN : public b  
{  
};  
```  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**, `struct`,`interface`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|**Co-Klasse** (wenn es sich um eine Klasse oder Struktur angewendet wird)|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [Klassenattribute](../windows/class-attributes.md)   
 [Methodenattribut](../windows/method-attributes.md)   
 [coclass](../windows/coclass.md)   
