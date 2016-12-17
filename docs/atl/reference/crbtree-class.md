---
title: "CRBTree Class"
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
  - "ATL.CRBTree"
  - "CRBTree"
  - "ATL::CRBTree"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRBTree class"
ms.assetid: a1b1cb63-38e4-4fc2-bb28-f774d1721760
caps.latest.revision: 18
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# CRBTree Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt Methoden zum Erstellen und das Verwenden einer RED\-Schwarz Struktur bereit.  
  
## Syntax  
  
```  
  
      template<  
   typename K,  
   typename V,  
   class KTraits = CElementTraits< K >,  
   class VTraits = CElementTraits< V >  
> class CRBTree  
```  
  
#### Parameter  
 `K`  
 Der Schlüsselelementtyp.  
  
 *V*  
 Der Wertselementtyp.  
  
 `KTraits`  
 Der Code verwendet, um Schlüsselelemente zu kopieren oder verschieben.  Siehe [CElementTraits\-Klasse](../../atl/reference/celementtraits-class.md) für weitere Details.  
  
 `VTraits`  
 Der Code verwendet, um Wertelemente zu kopieren oder verschieben.  
  
## Mitglieder  
  
### Öffentliche Typedefs  
  
|Name|Description|  
|----------|-----------------|  
|[CRBTree::KINARGTYPE](../Topic/CRBTree::KINARGTYPE.md)|Verwendeter Typ, wenn eine Taste als Eingabeargument übergeben wird.|  
|[CRBTree::KOUTARGTYPE](../Topic/CRBTree::KOUTARGTYPE.md)|Verwendeter Typ, wenn eine Taste als Ausgabeargument zurückgegeben wird.|  
|[CRBTree::VINARGTYPE](../Topic/CRBTree::VINARGTYPE.md)|Verwendeter Typ, wenn ein Wert als Eingabeargument übergeben wird.|  
|[CRBTree::VOUTARGTYPE](../Topic/CRBTree::VOUTARGTYPE.md)|Verwendeter Typ, wenn ein Wert als Ausgabeargument übergeben wird.|  
  
### Öffentliche Klassen  
  
|Name|Description|  
|----------|-----------------|  
|[CRBTree::CPair Class](../Topic/CRBTree::CPair%20Class.md)|Eine Klasse, die die Schlüssel und Wertelemente enthält.|  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CRBTree::~CRBTree](../Topic/CRBTree::~CRBTree.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CRBTree::FindFirstKeyAfter](../Topic/CRBTree::FindFirstKeyAfter.md)|Rufen Sie diese Methode auf, um die Position des Elements zu suchen, das die nächste verfügbare Schlüssel.|  
|[CRBTree::GetAt](../Topic/CRBTree::GetAt.md)|Rufen Sie diese Methode auf, um das Element in einer angegebenen Position in der Struktur abzurufen.|  
|[CRBTree::GetCount](../Topic/CRBTree::GetCount.md)|Rufen Sie diese Methode auf, um die Anzahl der Elemente in der Struktur abzurufen.|  
|[CRBTree::GetHeadPosition](../Topic/CRBTree::GetHeadPosition.md)|Rufen Sie diese Methode auf, um den Positionswert für das Element am Anfang der Struktur abzurufen.|  
|[CRBTree::GetKeyAt](../Topic/CRBTree::GetKeyAt.md)|Rufen Sie diese Methode auf, um die Schlüssel aus einer angegebenen Position in der Struktur abzurufen.|  
|[CRBTree::GetNext](../Topic/CRBTree::GetNext.md)|Rufen Sie diese Methode auf, um ein Zeiger auf ein Element abzurufen, das im `CRBTree`\-Objekt gespeichert ist, und setzen Sie die Position auf das nächste Element.|  
|[CRBTree::GetNextAssoc](../Topic/CRBTree::GetNextAssoc.md)|Rufen Sie diese Methode, um die Schlüssel und den Wert eines Elements abzurufen, auf das in der Zuordnung und Position zum nächsten Element in der gespeichert wird.|  
|[CRBTree::GetNextKey](../Topic/CRBTree::GetNextKey.md)|Rufen Sie diese Methode, um die Schlüssel eines Elements abzurufen, auf das in der Struktur und die Position auf das nächste Element zurückzusetzen gespeichert wird.|  
|[CRBTree::GetNextValue](../Topic/CRBTree::GetNextValue.md)|Rufen Sie diese Methode, um den Wert eines Elements abzurufen, auf das in der Struktur und die Position auf das nächste Element zurückzusetzen gespeichert wird.|  
|[CRBTree::GetPrev](../Topic/CRBTree::GetPrev.md)|Rufen Sie diese Methode auf, um ein Zeiger auf ein Element abzurufen, das im `CRBTree`\-Objekt gespeichert ist, und aktualisieren Sie dann die Position zum vorherigen Element.|  
|[CRBTree::GetTailPosition](../Topic/CRBTree::GetTailPosition.md)|Rufen Sie diese Methode auf, um den Positionswert für das Element am Ende der Struktur abzurufen.|  
|[CRBTree::GetValueAt](../Topic/CRBTree::GetValueAt.md)|Rufen Sie diese Methode auf, um den Wert abzurufen, der an einer angegebenen Position im `CRBTree`\-Objekt gespeichert wird.|  
|[CRBTree::IsEmpty](../Topic/CRBTree::IsEmpty.md)|Rufen Sie diese Methode auf, um ein leeres Strukturobjekt zu testen.|  
|[CRBTree::RemoveAll](../Topic/CRBTree::RemoveAll.md)|Rufen Sie diese Methode auf, um alle Elemente aus **CRBTree** \-Objekt zu entfernen.|  
|[CRBTree::RemoveAt](../Topic/CRBTree::RemoveAt.md)|Rufen Sie diese Methode auf, um das Element an der angegebenen Position im **CRBTree** \-Objekt zu entfernen.|  
|[CRBTree::SetValueAt](../Topic/CRBTree::SetValueAt.md)|Rufen Sie diese Methode auf, um den Wert zu ändern, der in einer bestimmten Position im `CRBTree`\-Objekt gespeichert wird.|  
  
## Hinweise  
 Eine RED\-Schwarz Struktur ist eine binäre Suchstruktur, die eine zusätzliche Informationen pro Knoten verwendet, um, sodass er "ausgeglichen bleibt", das heißt, die Strukturhöhe sicherzustellen wächst nicht unverhältnismäßig große und wirkt sich auf die Leistung aus.  
  
 Diese Vorlagenklasse wurde entworfen, durch [CRBMap](../../atl/reference/crbmap-class.md) und [CRBMultiMap](../../atl/reference/crbmultimap-class.md) verwendet werden.  Der Großteil der Methoden, die bilden, diese abgeleiteten Klassen werden von `CRBTree` bereitgestellt.  
  
 Weitere finden vollständige Erläuterung der verschiedenen Auflistungsklassen und ihre Funktionen und Leistungsmerkmale, [ATL\-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## Anforderungen  
 **Header:** atlcoll.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)