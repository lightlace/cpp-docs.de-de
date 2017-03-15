---
title: "nonextensible | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.nonextensible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "nonextensible attribute"
ms.assetid: c7ef1554-809f-4ea0-a7cd-dc7786d40c3e
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# nonextensible
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt an, dass die `IDispatch` nur die Implementierung der Eigenschaften und Methoden enthält, die in der Beschreibung der aufgelisteten Schnittstellen und nicht mit zusätzlichen Member zur Laufzeit erweitert werden kann.  
  
## Syntax  
  
```  
  
[nonextensible]  
  
```  
  
## Hinweise  
 Das Attribut **nicht erweiterbar** C\+\+ verfügt über die gleichen Funktionen wie das [nicht erweiterbar](http://msdn.microsoft.com/library/windows/desktop/aa367120) MIDL\-Attribut.  
  
 Verwendung von **nicht erweiterbar** erfordert außerdem das [oleautomation](../windows/oleautomation.md)\-Attribut.  
  
## Beispiel  
 Im folgenden Code wird die Verwendung des **nicht erweiterbar**\-Attribut angezeigt:  
  
```  
// cpp_attr_ref_nonextensible.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="ATLFIRELib")];  
[export] typedef long HRESULT;  
  
[dual, nonextensible, ms_union, oleautomation,   
uuid("00000000-0000-0000-0000-000000000001")]  
__interface IFireTabCtrl  
{  
   HRESULT procedure (int i);   
};  
```  
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|`interface`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|**dual** und **oleautomation**oder **dispinterface**|  
|**Ungültige Attribute**|None|  
  
 Weitere Informationen über das kontexte finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)