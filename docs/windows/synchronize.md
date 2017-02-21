---
title: "synchronize | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.synchronize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "synchronize attribute"
ms.assetid: 15fc8544-955d-4765-b3d5-0f619c8b3f40
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# synchronize
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Synchronisiert Zugriff auf die Zielmethode.  
  
## Syntax  
  
```  
  
[synchronize]  
  
```  
  
## Hinweise  
 Das Attribut **synchronisieren Sie** C\+\+ implementiert die Unterstützung für das Synchronisieren der Zielmethode eines Objekts.  Die Synchronisierung kann mehrere Objekte, um eine allgemeine Ressource \(z. B. eine Methode einer Klasse\), indem sie den Zugriff steuert die Zielmethode zu verwenden.  
  
 Der Code, der von diesem Attribut eingefügt wird, ruft die entsprechende Methode \( `Lock` bestimmt durch das Threadingmodell\) am Anfang der Zielmethode.  Wenn die Methode beendet wird, wird `Unlock` automatisch aufgerufen.  Weitere Informationen zu diesen Funktionen finden Sie unter [CComAutoThreadModule::Sperre](../Topic/CComAutoThreadModule::Lock.md)  
  
 Dieses Attribut erfordert, dass [Co\-Klasse](../windows/coclass.md), [ProgID](../windows/progid.md)oder [vi\_progid](../windows/vi-progid.md)\-Attribut \(oder ein anderes Attribut, das ein solcher Test vorhanden\), bedeutet auch auf das gleiche Element übernommen werden.  Wenn ein einzelnes Attribut wird, die anderen zwei automatisch angewendet werden.  Wenn z. B. **progid** angewendet wird, werden **vi\_progid** und **coclass** ebenfalls angewendet.  
  
## Beispiel  
 Der folgende Code stellt die Synchronisierung für die `UpdateBalance`\-Methode des `CMyClass`\-Objekts bereit.  
  
```  
// cpp_attr_ref_synchronize.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module(name="SYNC")];  
  
[coclass,  
 threading(both),  
 vi_progid("MyProject.MyClass"),  
 progid("MyProject.MyClass.1"),  
 uuid("7a7baa0d-59b8-4576-b754-79d07e1d1cc3")  
]  
class CMyClass {  
   float m_nBalance;  
  
   [synchronize]  
   void UpdateBalance(float nAdjust) {  
      m_nBalance += nAdjust;  
   }  
};  
```  
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|Klassenmethode, Methode|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Ein oder mehrere der folgenden Schritte aus: **coclass**, **progid**oder **vi\_progid**.|  
|**Ungültige Attribute**|None|  
  
 Weitere Informationen über das kontexte finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [COM Attributes](../windows/com-attributes.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)