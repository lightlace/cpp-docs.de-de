---
title: "CSimpleMap Class"
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
  - "ATL::CSimpleMap"
  - "ATL.CSimpleMap"
  - "CSimpleMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleMap class"
ms.assetid: 61b06eb4-ae73-44b0-a305-0afb5a33e8b1
caps.latest.revision: 21
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CSimpleMap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt Unterstützung für ein einfaches Zuordnungsarray.  
  
## Syntax  
  
```  
  
      template <   
   class TKey,  
   class TVal,  
   class TEqual = CSimpleMapEqualHelper< TKey, TVal >   
>   
class CSimpleMap  
```  
  
#### Parameter  
 `TKey`  
 Der Schlüsselelementtyp.  
  
 `TVal`  
 Der Wertselementtyp.  
  
 `TEqual`  
 Ein Merkmalsobjekt, den Übereinstimmungstest für Elemente des Typs `T` definiert.  
  
## Mitglieder  
  
### Öffentliche Typedefs  
  
|Name|Description|  
|----------|-----------------|  
|[CSimpleMap::\_ArrayElementType](../Topic/CSimpleMap::_ArrayElementType.md)|Typedef für den Werttyp.|  
|[CSimpleMap::\_ArrayKeyType](../Topic/CSimpleMap::_ArrayKeyType.md)|Typedef für den Schlüsseltyp.|  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CSimpleMap::CSimpleMap](../Topic/CSimpleMap::CSimpleMap.md)|Der \-Konstruktor.|  
|[CSimpleMap::~CSimpleMap](../Topic/CSimpleMap::~CSimpleMap.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CSimpleMap::Add](../Topic/CSimpleMap::Add.md)|Fügt einen Schlüssel und einen zugeordneten Wert dem Zuordnungsarray hinzu.|  
|[CSimpleMap::FindKey](../Topic/CSimpleMap::FindKey.md)|Wenn eine bestimmte Schlüssel.|  
|[CSimpleMap::FindVal](../Topic/CSimpleMap::FindVal.md)|Sucht einen bestimmten Wert.|  
|[CSimpleMap::GetKeyAt](../Topic/CSimpleMap::GetKeyAt.md)|Ruft den angegebenen Schlüssel ab.|  
|[CSimpleMap::GetSize](../Topic/CSimpleMap::GetSize.md)|Gibt die Anzahl der Einträge im Zuordnungsarray zurück.|  
|[CSimpleMap::GetValueAt](../Topic/CSimpleMap::GetValueAt.md)|Ruft den angegebenen Wert ab.|  
|[CSimpleMap::Lookup](../Topic/CSimpleMap::Lookup.md)|Gibt den Wert zurück, der dem angegebenen Schlüssel zugeordnet ist.|  
|[CSimpleMap::Remove](../Topic/CSimpleMap::Remove.md)|Entfernt einen Schlüssel und einen entsprechenden Wert.|  
|[CSimpleMap::RemoveAll](../Topic/CSimpleMap::RemoveAll.md)|Entfernt alle Schlüssel und Werte.|  
|[CSimpleMap::RemoveAt](../Topic/CSimpleMap::RemoveAt.md)|Entfernt einen bestimmten Schlüssel und einen entsprechenden Wert.|  
|[CSimpleMap::ReverseLookup](../Topic/CSimpleMap::ReverseLookup.md)|Gibt den Schlüssel zurück, die dem angegebenen Wert zugeordnet ist.|  
|[CSimpleMap::SetAt](../Topic/CSimpleMap::SetAt.md)|Legt den Wert fest, der dem angegebenen Schlüssel zugeordnet ist.|  
|[CSimpleMap::SetAtIndex](../Topic/CSimpleMap::SetAtIndex.md)|Legt die bestimmte Schlüssel und Wert fest.|  
  
## Hinweise  
 `CSimpleMap` bietet Unterstützung für ein einfaches Zuordnungsarray eines angegebenen Typs `T` und verwaltet ein Array ungeordnetes Schlüsselelemente und ihre zugeordneten Werte.  
  
 Der Parameter `TEqual` stellt Mittel zum Definieren einer Gleichheitsfunktion für zwei Elemente des Typs `T` bereit.  Durch Erstellen einer Klasse, die zu [CSimpleMapEqualHelper](../../atl/reference/csimplemapequalhelper-class.md) vergleichbar ist, ist es möglich, das Verhalten des Gleichheitstests für jedes angegebene Array zu ändern.  Beispielsweise bei der Behandlung von ein Array von Zeigern, es möglicherweise nützlich ist, Gleichheits\- wie je nach den Werten zu definieren, die Zeiger verweisen.  Die Standardimplementierung verwendet **operator\=\=\(\)**.  
  
 werden `CSimpleMap` und [CSimpleArray](../../atl/reference/csimplearray-class.md) für die Kompatibilität mit früheren ATL\-Versionen bereitgestellt, und vollständigere und effizientere Auflistungsimplementierungen werden von [CAtlArray](../../atl/reference/catlarray-class.md) und von [CAtlMap](../../atl/reference/catlmap-class.md) bereitgestellt.  
  
 Im Gegensatz zu anderen Zuordnungsauflistungen in ATL und in MFC, wird diese Klasse mit einem einfachen Array implementiert, und Suchensuchen erfordern eine lineare Suche.  `CAtlMap` sollte verwendet werden, wenn das Array viele Elemente enthält.  
  
## Anforderungen  
 **Header:** atlsimpcoll.h  
  
## Beispiel  
 [!CODE [NVC_ATL_Utilities#91](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#91)]  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)