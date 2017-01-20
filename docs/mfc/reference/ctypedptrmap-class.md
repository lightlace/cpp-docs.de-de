---
title: "CTypedPtrMap Class"
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
  - "CTypedPtrMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTypedPtrMap class"
  - "Zuordnungen"
  - "pointer maps"
  - "template classes, CTypedPtrMap class"
  - "type-safe collections"
ms.assetid: 9f377385-c6e9-4471-8b40-8fe220c50164
caps.latest.revision: 23
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# CTypedPtrMap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt einen typsicheren "Wrapper" für Objekte der ZeigerZuordnung Klassen `CMapPtrToPtr`, `CMapPtrToWord`, `CMapWordToPtr` und `CMapStringToPtr` bereit.  
  
## Syntax  
  
```  
template< class BASE_CLASS, class KEY, class VALUE >  
class CTypedPtrMap : public BASE_CLASS  
```  
  
#### Parameter  
 `BASE_CLASS`  
 Basisklasse der typisierten Zeigerzuordnungsklasse; muss eine Zeigerzuordnungsklasse \(`CMapPtrToPtr`, `CMapPtrToWord`, `CMapWordToPtr` oder `CMapStringToPtr`\).  
  
 `KEY`  
 Klasse des Objekts verwendet als Schlüssel zur Zuordnung.  
  
 `VALUE`  
 Klasse des Objekts gespeichert in der Zuordnung.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CTypedPtrMap::GetNextAssoc](../Topic/CTypedPtrMap::GetNextAssoc.md)|Ruft das folgende Element zum Durchlaufen ab.|  
|[CTypedPtrMap::Lookup](../Topic/CTypedPtrMap::Lookup.md)|Gibt `KEY` auf Grundlage `VALUE` zurück.|  
|[CTypedPtrMap::RemoveKey](../Topic/CTypedPtrMap::RemoveKey.md)|Entfernt ein Element, das über einen Schlüssel angegeben wird.|  
|[CTypedPtrMap::SetAt](../Topic/CTypedPtrMap::SetAt.md)|Fügt ein Element in die Zuordnung ein; ersetzt ein vorhandenes Element, wenn ein übereinstimmender Schlüssel gefunden wird.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CTypedPtrMap::operator](../Topic/CTypedPtrMap::operator.md)|Fügt ein Element in die Zuordnung ein.|  
  
## Hinweise  
 Wenn Sie `CTypedPtrMap` verwenden, beseitigen die C\+\+\-Typüberprüfungsfunktionshilfen die Fehler, die von nicht übereinstimmende Zeigertypen verursacht werden.  
  
 Da alle `CTypedPtrMap`\-Funktionen inline sind, hat Verwendung dieser Vorlage nicht wesentlich die Größe oder die Geschwindigkeit des Codes.  
  
 Weitere Informationen zur Verwendung von `CTypedPtrMap`, finden Sie in Artikel [Auflistungen](../../mfc/collections.md) und [Auf Vorlagen basierende Klassen](../../mfc/template-based-classes.md).  
  
## Vererbungshierarchie  
 `BASE_CLASS`  
  
 `CTypedPtrMap`  
  
## Anforderungen  
 **Header:**  afxtempl.h  
  
## Siehe auch  
 [MFC\-Beispiel COLLECT](../../top/visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CMapPtrToPtr Class](../../mfc/reference/cmapptrtoptr-class.md)   
 [CMapPtrToWord Class](../../mfc/reference/cmapptrtoword-class.md)   
 [CMapWordToPtr Class](../../mfc/reference/cmapwordtoptr-class.md)   
 [CMapStringToPtr Class](../../mfc/reference/cmapstringtoptr-class.md)