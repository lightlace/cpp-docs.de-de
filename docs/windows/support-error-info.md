---
title: Support_error_info | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.support_error_info
dev_langs:
- C++
helpviewer_keywords:
- support_error_info attribute
ms.assetid: 20a2b55c-4738-4b35-a71d-e5e9c3a7e3bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0c366a379d15e50aabdc3c2157f57f85b6b5b33b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33889929"
---
# <a name="supporterrorinfo"></a>support_error_info
Implementiert die Unterstützung für die Zurückgabe ausführlicher Fehler.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      [ support_error_info(  
   error_interface=uuid  
) ]  
```  
  
#### <a name="parameters"></a>Parameter  
 **error_interface**  
 Der Bezeichner der Schnittstelle, die **IErrorInfo**implementiert.  
  
## <a name="remarks"></a>Hinweise  
 Das **support_error_info** C++-Attribut implementiert die Unterstützung für die Zurückgabe ausführlicher, kontextbezogener Fehler am Zielobjekt an den Client. Für das Objekt, das Fehler unterstützt, müssen die Methoden der **IErrorInfo** -Schnittstelle implementiert werden. Weitere Informationen finden Sie unter [Unterstützung IDispatch und IErrorInfo](../atl/supporting-idispatch-and-ierrorinfo.md).  
  
 Dieses Attribut fügt dem Zielobjekt die [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) -Klasse als Basisklasse hinzu. Dies führt zu einer standardmäßigen Implementierung von **ISupportErrorInfo** und kann verwendet werden, wenn eine einzelne Schnittstelle Fehler bei einem Objekt generiert.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code fügt dem **-Objekt die Standardunterstützung für die** ISupportErrorInfo `CMyClass` -Schnittstelle hinzu.  
  
```  
// cpp_attr_ref_support_error_info.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module (name="mymod")];  
[object, uuid("f0b17d66-dc6e-4662-baaf-76758e09c878")]  
__interface IMyErrors  
{  
};  
  
[ coclass, support_error_info("IMyErrors"),  
  uuid("854dd392-bdc7-4781-8667-8757936f2a4f") ]  
class CMyClass  
{  
};  
```  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**|  
|**Wiederholbar**|Ja|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [COM-Attribute](../windows/com-attributes.md)   
 [Klassenattribute](../windows/class-attributes.md)   
