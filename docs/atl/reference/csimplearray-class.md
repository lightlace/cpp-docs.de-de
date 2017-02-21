---
title: "CSimpleArray Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CSimpleArray"
  - "ATL::CSimpleArray"
  - "CSimpleArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleArray class"
ms.assetid: ee0c9f39-b61c-4c18-bc43-4eada21dca3a
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CSimpleArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt Methoden zum Verwalten eines einfachen Arrays bereit.  
  
## Syntax  
  
```  
  
      template <  
   class T,  
   class TEqual = CSimpleArrayEqualHelper< T >  
>   
class CSimpleArray  
```  
  
#### Parameter  
 `T`  
 Der Typ im Array zum Speichern von Daten.  
  
 `TEqual`  
 Ein Merkmalsobjekt, den Übereinstimmungstest für Elemente des Typs `T` definiert.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CSimpleArray::CSimpleArray](../Topic/CSimpleArray::CSimpleArray.md)|Der Konstruktor für das einfache Array.|  
|[CSimpleArray::~CSimpleArray](../Topic/CSimpleArray::~CSimpleArray.md)|Der Destruktor für das einfache Array.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CSimpleArray::Add](../Topic/CSimpleArray::Add.md)|Fügt ein neues Element dem Array hinzu.|  
|[CSimpleArray::Find](../Topic/CSimpleArray::Find.md)|Sucht ein Element im Array.|  
|[CSimpleArray::GetData](../Topic/CSimpleArray::GetData.md)|Gibt einen Zeiger auf die Daten zurück, die im Array gespeichert sind.|  
|[CSimpleArray::GetSize](../Topic/CSimpleArray::GetSize.md)|Gibt die Anzahl von Elementen zurück, die im Array gespeichert sind.|  
|[CSimpleArray::Remove](../Topic/CSimpleArray::Remove.md)|Entfernt ein angegebenes Element aus dem Array.|  
|[CSimpleArray::RemoveAll](../Topic/CSimpleArray::RemoveAll.md)|Entfernt alle Elemente aus dem Array.|  
|[CSimpleArray::RemoveAt](../Topic/CSimpleArray::RemoveAt.md)|Entfernt das angegebene Element aus dem Array.|  
|[CSimpleArray::SetAtIndex](../Topic/CSimpleArray::SetAtIndex.md)|Legt das angegebene Element im Array fest.|  
  
### Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CSimpleArray::operator](../Topic/CSimpleArray::operator.md)|Ruft ein Element aus dem Array ab.|  
|[CSimpleArray::operator \=](../Topic/CSimpleArray::operator%20=.md)|Zuweisungsoperator.|  
  
## Hinweise  
 `CSimpleArray` stellt Methoden zum Erstellen und Verwalten eines einfachen Arrays, eines angegebenen Typs `T` bereit.  
  
 Der Parameter `TEqual` stellt Mittel zum Definieren einer Gleichheitsfunktion für zwei Elemente des Typs `T` bereit.  Durch Erstellen einer Klasse, die zu [CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md) vergleichbar ist, ist es möglich, das Verhalten des Gleichheitstests für jedes angegebene Array zu ändern.  Beispielsweise bei der Behandlung von ein Array von Zeigern, es möglicherweise nützlich ist, Gleichheits\- wie je nach den Werten zu definieren, die Zeiger verweisen.  Die Standardimplementierung verwendet **operator\=\(\)**.  
  
 sind `CSimpleArray` und [CSimpleMap](../../atl/reference/csimplemap-class.md) für eine kleine Anzahl Elemente vorgesehen.  [CAtlArray](../../atl/reference/catlarray-class.md) und [CAtlMap](../../atl/reference/catlmap-class.md) sollten verwendet werden, wenn das Array viele Elemente enthält.  
  
## Anforderungen  
 **Header:** atlsimpcoll.h  
  
## Beispiel  
 [!CODE [NVC_ATL_Utilities#86](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#86)]  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)