---
title: "CAtlMap Class"
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
  - "ATL.CAtlMap"
  - "CAtlMap"
  - "ATL::CAtlMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlMap class"
ms.assetid: 5e2fe028-8e6d-4686-93df-1433d2080ec3
caps.latest.revision: 21
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlMap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt Methoden zum Erstellen und Verwalten eines Zuordnungsobjekts bereit.  
  
## Syntax  
  
```  
  
      template<  
   typename K,  
   typename V,  
   class KTraits = CElementTraits< K >,  
   class VTraits = CElementTraits< V >  
>  
class CAtlMap  
```  
  
#### Parameter  
 `K`  
 Der Schlüsselelementtyp.  
  
 V  
 Der Wertselementtyp.  
  
 `KTraits`  
 Der Code verwendet, um Schlüsselelemente zu kopieren oder verschieben.  Siehe [CElementTraits\-Klasse](../../atl/reference/celementtraits-class.md) für weitere Details.  
  
 `VTraits`  
 Der Code verwendet, um Wertelemente zu kopieren oder verschieben.  
  
## Mitglieder  
  
### Öffentliche Typedefs  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlMap::KINARGTYPE](../Topic/CAtlMap::KINARGTYPE.md)|Verwendeter Typ, wenn eine Taste als Eingabeargument übergeben wird|  
|[CAtlMap::KOUTARGTYPE](../Topic/CAtlMap::KOUTARGTYPE.md)|Verwendeter Typ, wenn eine Taste als Ausgabeargument zurückgegeben wird.|  
|[CAtlMap::VINARGTYPE](../Topic/CAtlMap::VINARGTYPE.md)|Verwendeter Typ, wenn ein Wert als Eingabeargument übergeben wird.|  
|[CAtlMap::VOUTARGTYPE](../Topic/CAtlMap::VOUTARGTYPE.md)|Verwendeter Typ, wenn ein Wert als Ausgabeargument übergeben wird.|  
  
### Öffentliche Klassen  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlMap::CPair Class](../Topic/CAtlMap::CPair%20Class.md)|Eine Klasse, die die Schlüssel und Wertelemente enthält.|  
  
### CPair\-Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CPair::m\_key](../Topic/CAtlMap::CPair::m_key.md)|Der Datenmember, der das Schlüsselelement speichert.|  
|[CPair::m\_value](../Topic/CAtlMap::CPair::m_value.md)|Der Datenmember, der das Wertselement speichert.|  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlMap::CAtlMap](../Topic/CAtlMap::CAtlMap.md)|Der \-Konstruktor.|  
|[CAtlMap::~CAtlMap](../Topic/CAtlMap::~CAtlMap.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlMap::AssertValid](../Topic/CAtlMap::AssertValid.md)|Rufen Sie diese Methode auf, um eine ASSERT zu verursachen, wenn `CAtlMap` ungültig ist.|  
|[CAtlMap::DisableAutoRehash](../Topic/CAtlMap::DisableAutoRehash.md)|Rufen Sie diese Methode auf, um automatische Durchführen eines Rehash `CAtlMap` des Objekts zu deaktivieren.|  
|[CAtlMap::EnableAutoRehash](../Topic/CAtlMap::EnableAutoRehash.md)|Rufen Sie diese Methode auf, um automatische Durchführen eines Rehash `CAtlMap` des Objekts zu aktivieren.|  
|[CAtlMap::GetAt](../Topic/CAtlMap::GetAt.md)|Rufen Sie diese Methode auf, um das Element in einer angegebenen Position in der Zuordnung zurückzugeben.|  
|[CAtlMap::GetCount](../Topic/CAtlMap::GetCount.md)|Rufen Sie diese Methode auf, um die Anzahl der Elemente in der Zuordnung abzurufen.|  
|[CAtlMap::GetHashTableSize](../Topic/CAtlMap::GetHashTableSize.md)|Rufen Sie diese Methode auf, um die Anzahl von Containern in der Hashtabelle der Zuordnung zu bestimmen.|  
|[CAtlMap::GetKeyAt](../Topic/CAtlMap::GetKeyAt.md)|Rufen Sie diese Methode auf, um die Schlüssel abzurufen, die an der angegebenen Position im `CAtlMap`\-Objekt gespeichert wird.|  
|[CAtlMap::GetNext](../Topic/CAtlMap::GetNext.md)|Rufen Sie diese Methode auf, um ein Zeiger auf den folgenden Elementpaaren zu erhalten, die im `CAtlMap`\-Objekt gespeichert werden.|  
|[CAtlMap::GetNextAssoc](../Topic/CAtlMap::GetNextAssoc.md)|Ruft das folgende Element zum Durchlaufen ab.|  
|[CAtlMap::GetNextKey](../Topic/CAtlMap::GetNextKey.md)|Rufen Sie diese Methode auf, um die folgenden Schlüssel vom `CAtlMap`\-Objekt abzurufen.|  
|[CAtlMap::GetNextValue](../Topic/CAtlMap::GetNextValue.md)|Rufen Sie diese Methode auf, um den folgenden Wert vom `CAtlMap`\-Objekt abzurufen.|  
|[CAtlMap::GetStartPosition](../Topic/CAtlMap::GetStartPosition.md)|Rufen Sie diese Methode auf, um eine Zuordnungsiteration zu starten.|  
|[CAtlMap::GetValueAt](../Topic/CAtlMap::GetValueAt.md)|Rufen Sie diese Methode auf, um den Wert abzurufen, der an einer angegebenen Position im `CAtlMap`\-Objekt gespeichert wird.|  
|[CAtlMap::InitHashTable](../Topic/CAtlMap::InitHashTable.md)|Rufen Sie diese Methode auf, um die Hashtabelle zu initialisieren.|  
|[CAtlMap::IsEmpty](../Topic/CAtlMap::IsEmpty.md)|Rufen Sie diese Methode auf, um für leere Zuordnungsobjekt zu testen.|  
|[CAtlMap::Lookup](../Topic/CAtlMap::Lookup.md)|Rufen Sie diese Methode auf, um Schlüssel oder Werte im `CAtlMap`\-Objekt gesucht wird.|  
|[CAtlMap::Rehash](../Topic/CAtlMap::Rehash.md)|Rufen Sie diese Methode auf, um das `CAtlMap`\-Objekt aufzuwärmen.|  
|[CAtlMap::RemoveAll](../Topic/CAtlMap::RemoveAll.md)|Rufen Sie diese Methode auf, um alle Elemente aus `CAtlMap`\-Objekt zu entfernen.|  
|[CAtlMap::RemoveAtPos](../Topic/CAtlMap::RemoveAtPos.md)|Rufen Sie diese Methode auf, um das Element an der angegebenen Position im `CAtlMap`\-Objekt zu entfernen.|  
|[CAtlMap::RemoveKey](../Topic/CAtlMap::RemoveKey.md)|Rufen Sie diese Methode auf, um ein Element aus dem `CAtlMap`\-Objekt zu entfernen, die Schlüssel angegeben.|  
|[CAtlMap::SetAt](../Topic/CAtlMap::SetAt.md)|Rufen Sie diese Methode auf, um ein Elementpaar in die Zuordnung einzufügen.|  
|[CAtlMap::SetOptimalLoad](../Topic/CAtlMap::SetOptimalLoad.md)|Rufen Sie diese Methode auf, um die optimale Auslastung des `CAtlMap`\-Objekts festzulegen.|  
|[CAtlMap::SetValueAt](../Topic/CAtlMap::SetValueAt.md)|Rufen Sie diese Methode auf, um den Wert zu ändern, der in einer bestimmten Position im `CAtlMap`\-Objekt gespeichert wird.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlMap::operator](../Topic/CAtlMap::operator.md)|Ersetzt oder wird ein neues Element `CAtlMap` hinzu.|  
  
## Hinweise  
 `CAtlMap` bietet Unterstützung für ein Zuordnungsarray eines angegebenen Typs und verwaltet ein Array ungeordnetes Schlüsselelemente und ihre zugeordneten Werte.  Elemente \(einem Schlüssel und einem Wert bestehend\) werden mithilfe eines Hashalgorithmus gespeichert und ermöglichen eine große Menge an effizient gespeichert werden und sind Daten abgerufen worden.  
  
 Die `KTraits` und `VTraits`\-Parameter sind Merkmalklassen, die jeden ergänzenden Code enthalten, der erforderlich ist, um Elemente zu kopieren oder verschieben.  
  
 Eine Alternative zu `CAtlMap` wird durch die [CRBMap](../../atl/reference/crbmap-class.md)\-Klasse bereitgestellte.  `CRBMap` speichert auch Schlüssel\-Wert\-Paare, aber unterschiedliche Leistungsmerkmale der Ausstellungen.  Die Zeit, die verwendet wird, um ein Element einzufügen, ein Schlüssel gesucht wird, oder einen Schlüssel aus einem `CRBMap`\-Objekt zu löschen, ist von der Ordnung  *log\(n\)*, wobei *n* die Anzahl der Elemente ist.  Für `CAtlMap` dauern alle diese Vorgänge in der Regel eine konstante Zeit, obwohl schlechtestmögliche Entwicklungsverläufe möglicherweise von der Ordnung *n* sind.  Daher in einem typischen Fall, ist `CAtlMap` schneller.  
  
 Der andere Unterschied zwischen `CRBMap` und `CAtlMap` wird beim Durchlaufen der gespeicherten Elemente erleichtern.  In `CRBMap` werden die Elemente in einer sortierten Reihenfolge überprüft.  In `CAtlMap` werden die Elemente nicht sortiert, und keine Reihenfolge kann abgeleitet werden.  
  
 Wenn eine kleine Anzahl Elemente gespeichert werden müssen, erwägen Sie, die [CSimpleMap](../../atl/reference/csimplemap-class.md)\-Klasse stattdessen zu verwenden.  
  
 Weitere Informationen finden Sie unter [ATL\-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## Anforderungen  
 **Header:** atlcoll.h  
  
## Siehe auch  
 [Marquee\-Beispiel](../../top/visual-cpp-samples.md)   
 [UpdatePV\-Beispiel](../../top/visual-cpp-samples.md)   
 [Class Overview](../../atl/atl-class-overview.md)