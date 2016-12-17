---
title: "source (C++)"
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
  - "vc-attr.source"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "source attribute"
ms.assetid: 1878d05d-7709-4e97-b114-c62f38f5140e
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# source (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Auf einer Klasse gibt die Schnittstellen des COM\-Objekts Quelle für Verbindungspunkte an.  Auf einer Eigenschaft oder einer Methode gibt an, dass der Member ein Objekt oder einen VARIANT zurück, das eine Ereignisquelle ist.  
  
## Syntax  
  
```  
  
      [ source(  
   interfaces  
) ]  
```  
  
#### Parameter  
 `interfaces`  
 Eine oder mehrere Schnittstellen, mit denen Sie angeben, wann Sie das Attribut Quelle auf eine Klasse anwenden.  Dieser Parameter wird nicht verwendet, wenn Quelle auf eine Eigenschaft oder eine Methode angewendet wird.  
  
## Hinweise  
 Das Attribut **Quelle** C\+\+ verfügt über die gleichen Funktionen wie das [Quelle](http://msdn.microsoft.com/library/windows/desktop/aa367166) MIDL\-Attribut.  
  
 Sie können das [Standardwert](../windows/default-cpp.md)\-Attribut verwenden, um die standardmäßige Quellschnittstelle für ein Objekt anzugeben.  
  
## Beispiel  
  
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
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**, `struct`, `interface`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|**coclass** \(wenn die Klasse oder Struktur angewendet werden\)|  
|**Ungültige Attribute**|None|  
  
 Weitere Informationen über das kontexte finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [coclass](../windows/coclass.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)