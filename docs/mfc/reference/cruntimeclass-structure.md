---
title: "CRuntimeClass Structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CRuntimeClass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRuntimeClass structure"
  - "dynamic class information"
  - "run-time class, CRuntimeClass structure"
  - "Laufzeit, class information"
ms.assetid: de62b6ef-90d4-420f-8c70-f58b36976a2b
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CRuntimeClass Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Jede Klasse, die von `CObject` berechnet wird, wird mit einer `CRuntimeClass`\-Struktur zugeordnet, die Sie verwenden können, um zur Laufzeit zu erhalten Informationen zu einem Objekt oder seine Basisklasse.  
  
## Syntax  
  
```  
struct CRuntimeClass  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CRuntimeClass::CreateObject](../Topic/CRuntimeClass::CreateObject.md)|Erstellt ein Objekt während der Laufzeit.|  
|[CRuntimeClass::FromName](../Topic/CRuntimeClass::FromName.md)|Erstellt ein Objekt zur Laufzeit mithilfe von vertrauten Klassennamens.|  
|[CRuntimeClass::IsDerivedFrom](../Topic/CRuntimeClass::IsDerivedFrom.md)|Bestimmt, ob die Klasse von der angegebenen Klasse abgeleitet wird.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CRuntimeClass::m\_lpszClassName](../Topic/CRuntimeClass::m_lpszClassName.md)|Der Name der Klasse.|  
|[CRuntimeClass::m\_nObjectSize](../Topic/CRuntimeClass::m_nObjectSize.md)|Die Größe des Objekts in Bytes.|  
|[CRuntimeClass::m\_pBaseClass](../Topic/CRuntimeClass::m_pBaseClass.md)|Ein Zeiger auf die `CRuntimeClass`\-Struktur der Basisklasse.|  
|[CRuntimeClass::m\_pfnCreateObject](../Topic/CRuntimeClass::m_pfnCreateObject.md)|Ein Zeiger auf eine Funktion, die dynamisch das Objekt erstellt.|  
|[CRuntimeClass::m\_pfnGetBaseClass](../Topic/CRuntimeClass::m_pfnGetBaseClass.md)|Gibt die `CRuntimeClass`\-Struktur zurück \(nur verfügbar, wenn Sie dynamisch verknüpft sind\).|  
|[CRuntimeClass::m\_wSchema](../Topic/CRuntimeClass::m_wSchema.md)|Die Schemazahl der Klasse.|  
  
## Hinweise  
 `CRuntimeClass` ist eine Struktur daher verfügt keine Basisklasse.  
  
 Die Möglichkeit, die Klasse eines Objekts zu bestimmen zur Laufzeit ist nützlich, wenn zusätzliche Typüberprüfung von Funktionsargumenten benötigt wird oder wenn Sie für besondere Zwecke auf Grundlage der Klasse eines Objekts Code schreiben müssen.  Ablaufklasseninformationen werden nicht direkt über die Programmiersprache C\+\+ unterstützt.  
  
 `CRuntimeClass` enthält Informationen über das verknüpfte C\+\+\-Objekt, wie einem Zeiger auf `CRuntimeClass` der Basisklasse und des ASCII\-Klassennamens verwandter Klasse bereit.  Diese Struktur implementiert auch verschiedene Funktionen, die verwendet werden können, um die Objekte dynamisch zu erstellen und den Typ des Objekts angeben, indem Sie einen bekannten Namen verwendet, und wenn die verwandte Klasse von einer bestimmten Klasse bestimmt, berechnet wird.  
  
 Weitere Informationen zur Verwendung von `CRuntimeClass`, finden Sie im Artikel [Zugreifen auf Ablaufklasseninformationen](../../mfc/accessing-run-time-class-information.md).  
  
## Vererbungshierarchie  
 `CRuntimeClass`  
  
## Anforderungen  
 **Header:**  afx.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CObject::GetRuntimeClass](../Topic/CObject::GetRuntimeClass.md)   
 [CObject::IsKindOf](../Topic/CObject::IsKindOf.md)   
 [RUNTIME\_CLASS](../Topic/RUNTIME_CLASS.md)   
 [IMPLEMENT\_DYNAMIC](../Topic/IMPLEMENT_DYNAMIC.md)   
 [IMPLEMENT\_DYNCREATE](../Topic/IMPLEMENT_DYNCREATE.md)   
 [IMPLEMENT\_SERIAL](../Topic/IMPLEMENT_SERIAL.md)