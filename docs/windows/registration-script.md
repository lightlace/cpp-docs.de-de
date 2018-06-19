---
title: Registration_script | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.registration_script
dev_langs:
- C++
helpviewer_keywords:
- registration_script attribute
ms.assetid: 786f8072-9187-4163-a979-7a604dd4c888
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d4385dd12fccafb154a637dd5260764667d3887a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878722"
---
# <a name="registrationscript"></a>registration_script
Führt die angegebene benutzerdefinierte Registrierung-Skript aus.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      [ registration_script(   
   script   
) ]  
```  
  
#### <a name="parameters"></a>Parameter  
 *Skript*  
 Der vollständige Pfad zu einer benutzerdefinierten Registrierungsskriptdatei (.rgs). Der Wert **keine**, wie z. B. `script = "none"`, gibt an, dass die Co-Klasse keine Registrierung erforderlich ist.  
  
## <a name="remarks"></a>Hinweise  
 Die **Registration_script** C++-Attribut führt gemäß benutzerdefinierten Registrierungsskript **Skript**. Wenn dieses Attribut nicht angegeben ist, wird eine standard RGS-Datei (mit Informationen zum Registrieren der Komponente) verwendet. Weitere Informationen zu RGS-Dateien finden Sie unter [der ATL-Registrierungskomponente (Registrar)](../atl/atl-registry-component-registrar.md).  
  
 Dieses Attribut erfordert, dass die Attribute [coclass](../windows/coclass.md), [progid](../windows/progid.md), oder [vi_progid](../windows/vi-progid.md) (oder ein anderes Attribut, das eines der genannten impliziert) auch auf demselben Element angewendet werden.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code gibt an, dass die Komponente eine Registrierungsdatei cpp_attr_ref_registration_script.rgs aufgerufen hat.  
  
```  
// cpp_attr_ref_registration_script.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module (name="REG")];  
  
[object, uuid("d9cd196b-6836-470b-9b9b-5b04b828e5b0")]  
__interface IFace {};  
  
// requires "cpp_attr_ref_registration_script.rgs"  
// create sample .RGS file "cpp_attr_ref_registration_script.rgs" if it does not exist  
[ coclass, registration_script(script="cpp_attr_ref_registration_script.rgs"),  
  uuid("50d3ad42-3601-4f26-8cfe-0f1f26f98f67")]  
class CMyClass:public IFace {};  
```  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**, `struct`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Ein Attribut oder mehrere Attribute der folgenden: **coclass**, **progid**, oder **vi_progid**.|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [COM-Attribute](../windows/com-attributes.md)   
 [Klassenattribute](../windows/class-attributes.md)   
 [rdx](../windows/rdx.md)   
