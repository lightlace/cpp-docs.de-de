---
title: "CObject Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Basisklassen, MFC-Objekte"
  - "CObject class"
  - "object classes"
  - "Objekte [C++], base class for MFC"
ms.assetid: 95e9acd3-d9eb-4ac0-b52b-ca4a501a7a3a
caps.latest.revision: 22
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# CObject Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Prinzipale Basisklasse für Microsoft Foundation Class\-Bibliothek.  
  
## Syntax  
  
```  
class AFX_NOVTABLE CObject  
```  
  
## Mitglieder  
  
### Geschützte Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CObject::CObject](../Topic/CObject::CObject.md)|Standardkonstruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CObject::AssertValid](../Topic/CObject::AssertValid.md)|Überprüft die Integrität dieses Objekts.|  
|[CObject::Dump](../Topic/CObject::Dump.md)|Erzeugt einen Diagnosen Dump dieses Objekts.|  
|[CObject::GetRuntimeClass](../Topic/CObject::GetRuntimeClass.md)|Gibt die `CRuntimeClass`\-Struktur entsprechend dem Objekts zurück.|  
|[CObject::IsKindOf](../Topic/CObject::IsKindOf.md)|Testet die Beziehung dieses Objekts auf einer bestimmten Klasse.|  
|[CObject::IsSerializable](../Topic/CObject::IsSerializable.md)|Tests, festzustellen, ob dieses Objekt serialisiert werden kann.|  
|[CObject::Serialize](../Topic/CObject::Serialize.md)|lädt oder speichert ein Objekt von\/nach einem Archiv.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CObject::operator delete](../Topic/CObject::operator%20delete.md)|Spezieller **delete**\-Operator.|  
|[CObject::operator new](../Topic/CObject::operator%20new.md)|Spezieller **new**\-Operator.|  
  
## Hinweise  
 Sie dient als Stamm nicht nur für Bibliotheksklassen wie `CFile` und `CObList`, sondern auch für die Klassen, die Sie schreiben.  `CObject` stellt die Basisdienste und enthält  
  
-   Serialisierungsunterstützung  
  
-   Ablaufklasseninformationen  
  
-   Objektdiagnosenausgabe  
  
-   Kompatibilität mit Auflistungsklassen  
  
 Beachten Sie, dass `CObject` Mehrfachvererbung nicht unterstützt.  die abgeleiteten Klassen können nur eine `CObject` Basisklasse haben, und die `CObject` muss in der Hierarchie ganz links steht sein.  Es ist jedoch zulässig Strukturen und Nicht \-\-`CObject` verfügen von abgeleitete Klassen in den rechten Mehrfachvererbungsverzweigungen.  
  
 Sie stellen wichtige Vorteile von `CObject` Ableitung, wenn Sie einige optionale Makros in der Klassenimplementierung und in Deklarationen verwenden.  
  
 Die Makros der obersten Ebene, [DECLARE\_DYNAMIC](../Topic/DECLARE_DYNAMIC.md) und [IMPLEMENT\_DYNAMIC](../Topic/IMPLEMENT_DYNAMIC.md), der Erlaubnisablaufzugriff dem Klassennamen und seine Position in der Hierarchie.  Dadurch kann wiederum sinnvollen Diagnosedump.  
  
 Die Makros der zweiten Ebene, [DECLARE\_SERIAL](../Topic/DECLARE_SERIAL.md) und [IMPLEMENT\_SERIAL](../Topic/IMPLEMENT_SERIAL.md), enthalten die gesamte Funktionalität der Makros der obersten Ebene, und sie aktivieren, um ein Objekt zu und von einem "Archive "serialisiert"."  
  
 Weitere Informationen zum Microsoft Foundations\-Klassen und C\+\+\-Klassen im Allgemeinen ableiten und die Verwendung von `CObject`, finden Sie unter [Verwenden von CObject](../../mfc/using-cobject.md) und [Serialisierung](../../mfc/serialization-in-mfc.md).  
  
## Vererbungshierarchie  
 `CObject`  
  
## Anforderungen  
 **Header:**  afx.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)