---
title: ReadOnly (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.readonly
dev_langs:
- C++
helpviewer_keywords:
- readonly attribute
ms.assetid: 1246cadd-5304-43a9-beea-51153d12704d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 87933b214dfe91f1c9f7db88127ef83da5b7201c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33876565"
---
# <a name="readonly-c"></a>readonly (C++)
Verhindert die Zuweisung zu einem Datenelement  
  
## <a name="syntax"></a>Syntax  
  
```  
  
[readonly]  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Das C++-Attribut **readonly** hat die gleiche Funktion wie das MIDL-Attribut [readonly](http://msdn.microsoft.com/library/windows/desktop/aa367152) .  
  
 Wenn Sie die Änderung eines Methodenparameters verhindern möchten, verwenden Sie das [in](../windows/in-cpp.md) -Attribut.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt die Verwendung des **readonly** -Attributs:  
  
```  
// cpp_attr_ref_readonly.cpp  
// compile with: /LD  
[idl_quote("midl_pragma warning(disable:2461)")];  
#include "unknwn.h"  
[module(name="ATLFIRELib")];  
  
[dispinterface, uuid(11111111-1111-1111-1111-111111111111)]  
__interface IFireTabCtrl  
{  
   [readonly, id(1)] int i();  
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
 [Datenmemberattribute](../windows/data-member-attributes.md)   
