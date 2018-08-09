---
title: Requires_category | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.requires_category
dev_langs:
- C++
helpviewer_keywords:
- requires_category attribute
ms.assetid: a645fdc6-1ef5-414d-8c56-5fe2686d4687
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2e2fd0863608f7e48d8ee2b296d1e1e76de6e541
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40018480"
---
# <a name="requirescategory"></a>requires_category
Gibt die erforderliche Komponentenkategorien der Zielklasse.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
[ requires_category(   
  requires_category  
) ]  
```  
  
### <a name="parameters"></a>Parameter  
 *requires_category*  
 Die ID der Kategorie erforderlich.  
  
## <a name="remarks"></a>Hinweise  
 Die **Requires_category** C++-Attribut gibt die Komponentenkategorien, die erforderlich sind, indem Sie die Zielklasse an. Weitere Informationen finden Sie unter [REQUIRED_CATEGORY](../atl/reference/category-macros.md#required_category).  
  
 Dieses Attribut erfordert, dass die Attribute [coclass](../windows/coclass.md), [progid](../windows/progid.md), oder [vi_progid](../windows/vi-progid.md) (oder ein anderes Attribut, das eines der genannten impliziert) auch auf demselben Element angewendet werden.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code erfordert, dass das Objekt die Kategorie "Steuerelement" implementieren.  
  
```cpp  
// cpp_attr_ref_requires_category.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module (name="MyLibrary")];  
  
[ coclass, requires_category("CATID_Control"),  
  uuid("1e1a2436-f3ea-4ff3-80bf-5409370e8144")]  
class CMyClass {};  
```  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**, **Struktur**|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Eine oder mehrere der folgenden: `coclass`, `progid`, oder `vi_progid`.|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [COM-Attribute](../windows/com-attributes.md)   
 [implements_category](../windows/implements-category.md)   