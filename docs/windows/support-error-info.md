---
title: "support_error_info"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.support_error_info"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "support_error_info-Attribut"
ms.assetid: 20a2b55c-4738-4b35-a71d-e5e9c3a7e3bc
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# support_error_info
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Implementiert die Unterstützung für die Zurückgabe ausführlicher Fehler.  
  
## Syntax  
  
```  
  
[ support_error_info(  
   error_interface=  
uuid  
) ]  
  
```  
  
#### Parameter  
 **error\_interface**  
 Der Bezeichner der Schnittstelle, die **IErrorInfo** implementiert.  
  
## Hinweise  
 Das **support\_error\_info** C\+\+\-Attribut implementiert die Unterstützung für die Zurückgabe ausführlicher, kontextbezogener Fehler am Zielobjekt an den Client. Für das Objekt, das Fehler unterstützt, müssen die Methoden der **IErrorInfo**\-Schnittstelle implementiert werden. Weitere Informationen finden Sie unter [Unterstützung IDispatch und IErrorInfo](../atl/supporting-idispatch-and-ierrorinfo.md).  
  
 Dieses Attribut fügt dem Zielobjekt die [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md)\-Klasse als Basisklasse hinzu. Dies führt zu einer standardmäßigen Implementierung von **ISupportErrorInfo** und kann verwendet werden, wenn eine einzelne Schnittstelle Fehler bei einem Objekt generiert.  
  
## Beispiel  
 Der folgende Code fügt dem `CMyClass`\-Objekt die Standardunterstützung für die **ISupportErrorInfo**\-Schnittstelle hinzu.  
  
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
  
## Anforderungen  
  
### Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**|  
|**Wiederholbar**|Ja|  
|**Erforderliche Attribute**|Keine|  
|**Ungültige Attribute**|Keine|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [COM Attributes](../windows/com-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)