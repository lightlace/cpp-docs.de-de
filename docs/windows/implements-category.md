---
title: Implements_category | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.implements_category
dev_langs: C++
helpviewer_keywords: implements_category attribute
ms.assetid: fb162df3-1ebe-43dc-a084-668d7ef8c03f
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6ab6206851385dcf7bf73cf56730093e7fc5c48f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="implementscategory"></a>implements_category
Gibt die Komponentenkategorien, die von der Zielklasse implementiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      [ implements_category(  
   implements_category="uuid"  
) ]  
```  
  
#### <a name="parameters"></a>Parameter  
 **implements_category**  
 Die ID der Kategorie implementiert.  
  
## <a name="remarks"></a>Hinweise  
 Die **Implements_category** C++-Attribut gibt an, die von der Zielklasse implementiert Komponentenkategorien. Dies erfolgt durch Erstellen einer Kategorie Zuordnung und Hinzufügen von trennen Sie die Einträge gemäß der **Implements_category** Attribut. Weitere Informationen finden Sie unter [was Komponentenkategorien und führen sie Funktionsweise sind?](http://msdn.microsoft.com/library/windows/desktop/ms694322).  
  
 Dieses Attribut erfordert, dass die Attribute [coclass](../windows/coclass.md), [progid](../windows/progid.md), oder [vi_progid](../windows/vi-progid.md) (oder ein anderes Attribut, das eines der genannten impliziert) auch auf demselben Element angewendet werden. Wenn ein einzelnes Attribut verwendet wird, werden die anderen beiden automatisch angewendet. Wenn z.B. **progid** angewendet wird, werden **vi_progid** und **coclass** ebenso angewendet.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code gibt an, dass das folgende Objekt die Steuerelement-Kategorie implementiert.  
  
```  
// cpp_attr_ref_implements_category.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module (name="MyLib")];  
[ coclass, implements_category("CATID_Control"),  
  uuid("20a0d0cc-5172-40f5-99ae-5e032f3205ae")]  
class CMyClass {};  
```  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**, `struct`|  
|**Wiederholbar**|Ja|  
|**Erforderliche Attribute**|Eines der folgenden: **Coclass**, **progid**, oder **Vi_progid**|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [COM-Attribute](../windows/com-attributes.md)   
 [Klassenattribute](../windows/class-attributes.md)   
 [IMPLEMENTED_CATEGORY](../atl/reference/category-macros.md#implemented_category)   
 