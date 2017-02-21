---
title: "CComSafeArray-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComSafeArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComSafeArray-Klasse"
ms.assetid: ee349aef-33db-4c85-bd08-5d86a3c9d53a
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 29
---
# CComSafeArray-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse ist ein Wrapper für die **SAFEARRAY**\-Struktur.  
  
## Syntax  
  
```  
template <  
   typename T,  
   VARTYPE _vartype = _ATL_AutomationType< T >::type  
>  
class CComSafeArray  
```  
  
#### Parameter  
 `T`  
 Der Typ der im Array gespeicherten Daten.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CComSafeArray::CComSafeArray](../Topic/CComSafeArray::CComSafeArray.md)|Der Konstruktor.|  
|[CComSafeArray::~CComSafeArray](../Topic/CComSafeArray::~CComSafeArray.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CComSafeArray::Add](../Topic/CComSafeArray::Add.md)|Fügt dem `CComSafeArray` eine oder mehrere Elemente oder eine **SAFEARRAY**\-Struktur hinzu.|  
|[CComSafeArray::Attach](../Topic/CComSafeArray::Attach.md)|Hängt einem `CComSafeArray`\-Objekt eine **SAFEARRAY**\-Struktur an.|  
|[CComSafeArray::CopyFrom](../Topic/CComSafeArray::CopyFrom.md)|Kopiert den Inhalt einer **SAFEARRAY**\-Struktur in das `CComSafeArray`\-Objekt.|  
|[CComSafeArray::CopyTo](../Topic/CComSafeArray::CopyTo.md)|Erstellt eine Kopie des `CComSafeArray`\-Objekts.|  
|[CComSafeArray::Create](../Topic/CComSafeArray::Create.md)|Erstellt ein `CComSafeArray`\-Objekt.|  
|[CComSafeArray::Destroy](../Topic/CComSafeArray::Destroy.md)|Zerstört ein `CComSafeArray`\-Objekt.|  
|[CComSafeArray::Detach](../Topic/CComSafeArray::Detach.md)|Trennt ein **SAFEARRAY** von einem `CComSafeArray`\-Objekt.|  
|[CComSafeArray::GetAt](../Topic/CComSafeArray::GetAt.md)|Ruft ein einzelnes Element aus einem eindimensionalen Array ab.|  
|[CComSafeArray::GetCount](../Topic/CComSafeArray::GetCount.md)|Gibt die Anzahl der Elemente des Arrays zurück.|  
|[CComSafeArray::GetDimensions](../Topic/CComSafeArray::GetDimensions.md)|Gibt die Anzahl der Dimensionen des Arrays zurück.|  
|[CComSafeArray::GetLowerBound](../Topic/CComSafeArray::GetLowerBound.md)|Gibt die untere Grenze für eine bestimmte Dimension des Arrays zurück.|  
|[CComSafeArray::GetSafeArrayPtr](../Topic/CComSafeArray::GetSafeArrayPtr.md)|Gibt die Adresse des `m_psa`\-Datenelements zurück.|  
|[CComSafeArray::GetType](../Topic/CComSafeArray::GetType.md)|Gibt den Typ der im Array gespeicherten Daten zurück.|  
|[CComSafeArray::GetUpperBound](../Topic/CComSafeArray::GetUpperBound.md)|Gibt die obere Grenze für eine bestimmte Dimension des Arrays zurück.|  
|[CComSafeArray::IsSizable](../Topic/CComSafeArray::IsSizable.md)|Testet, ob die Größe eines `CComSafeArray`\-Objekts geändert werden kann.|  
|[CComSafeArray::MultiDimGetAt](../Topic/CComSafeArray::MultiDimGetAt.md)|Ruft ein einzelnes Element aus einem mehrdimensionalen Array ab.|  
|[CComSafeArray::MultiDimSetAt](../Topic/CComSafeArray::MultiDimSetAt.md)|Legt den Wert eines Elements in einem mehrdimensionalen Array fest.|  
|[CComSafeArray::Resize](../Topic/CComSafeArray::Resize.md)|Ändert die Größe eines `CComSafeArray`\-Objekts.|  
|[CComSafeArray::SetAt](../Topic/CComSafeArray::SetAt.md)|Legt den Wert eines Elements in einem eindimensionalen Array fest.|  
  
### Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CComSafeArray::operator LPSAFEARRAY](../Topic/CComSafeArray::operator%20LPSAFEARRAY.md)|Wandelt einen Wert in einen **SAFEARRAY**\-Zeiger um.|  
|[CComSafeArray::operator](../Topic/CComSafeArray::operator.md)|Ruft ein Element aus dem Array ab.|  
|[CComSafeArray::operator \=](../Topic/CComSafeArray::operator%20=.md)|Zuweisungsoperator.|  
  
### Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CComSafeArray::m\_psa](../Topic/CComSafeArray::m_psa.md)|Dieses Datenelement enthält die Adresse der **SAFEARRAY**\-Struktur.|  
  
## Hinweise  
 `CComSafeArray` stellt einen Wrapper für die [SAFEARRAY Data Type](assetId:///9ec8025b-4763-4526-ab45-390c5d8b3b1e)\-Klasse bereit, wodurch sich ein\- und mehrdimensionale Arrays von nahezu jedem der VARIANT\-unterstützten Typen problemlos erstellen und verwalten lassen.  
  
 `CComSafeArray` vereinfacht die Übergabe von Arrays zwischen Prozessen und bietet darüber hinaus zusätzliche Sicherheit durch Überprüfen der Arrayindexwerte anhand der oberen und unteren Grenzen.  
  
 Die untere Grenze eines `CComSafeArray` kann bei einem beliebigen benutzerdefinierten Wert beginnen, Arrays, auf die über C\+\+ zugegriffen wird, sollte jedoch eine Untergrenze von 0 verwenden. Andere Sprachen wie Visual Basic können andere Begrenzungswerte \(z. B. \-10 bis 10\) verwenden.  
  
 Verwenden Sie [CComSafeArray::Create](../Topic/CComSafeArray::Create.md), um ein `CComSafeArray`\-Objekt zu erstellen, und [CComSafeArray::Destroy](../Topic/CComSafeArray::Destroy.md), um es zu löschen.  
  
 Ein `CComSafeArray` kann die folgende Teilmenge von VARIANT\-Datentypen enthalten:  
  
|VARTYPE|Beschreibung|  
|-------------|------------------|  
|VT\_I1|char|  
|VT\_I2|short|  
|VT\_I4|int|  
|VT\_I4|long|  
|VT\_I8|longlong|  
|VT\_UI1|byte|  
|VT\_UI2|ushort|  
|VT\_UI4|uint|  
|VT\_UI4|ulong|  
|VT\_UI8|ulonglong|  
|VT\_R4|float|  
|VT\_R8|double|  
|VT\_DECIMAL|Dezimalzeiger|  
|VT\_VARIANT|Variant\-Zeiger|  
|VT\_CY|Currency\-Datentyp|  
  
## Anforderungen  
 **Header:** atlsafe.h  
  
## Beispiel  
 [!CODE [NVC_ATL_Utilities#75](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#75)]  
  
## Siehe auch  
 [SAFEARRAY Data Type](assetId:///9ec8025b-4763-4526-ab45-390c5d8b3b1e)   
 [CComSafeArray::Create](../Topic/CComSafeArray::Create.md)   
 [CComSafeArray::Destroy](../Topic/CComSafeArray::Destroy.md)   
 [Class Overview](../../atl/atl-class-overview.md)