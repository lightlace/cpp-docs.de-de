---
title: "CTypedPtrList Class"
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
  - "CTypedPtrList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTypedPtrList class"
  - "linked lists [C++]"
  - "lists [C++]"
  - "pointer lists"
  - "template classes, CTypedPtrList class"
  - "type-safe collections"
ms.assetid: c273096e-1756-4340-864b-4a08b674a65e
caps.latest.revision: 24
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# CTypedPtrList Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt einen typsicheren "Wrapper" für Objekte der Klasse `CPtrList` bereit.  
  
## Syntax  
  
```  
template< class BASE_CLASS, class TYPE >  
class CTypedPtrList : public BASE_CLASS  
```  
  
#### Parameter  
 `BASE_CLASS`  
 Basisklasse der typisierten Zeigerlistenklasse; muss eine Zeigerlistenklasse \(`CObList` oder `CPtrList`\).  
  
 `TYPE`  
 Typ der Elemente in der Basisklassenliste.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CTypedPtrList::AddHead](../Topic/CTypedPtrList::AddHead.md)|Fügt ein Element \(oder alle Elemente in anderen Liste\) den Kopf der Liste hinzu \(erstellt einen neuen Kopf erstellt\).|  
|[CTypedPtrList::AddTail](../Topic/CTypedPtrList::AddTail.md)|Fügt ein Element \(oder alle Elemente in anderen Liste\) dem Ende der Liste hinzu \(erstellt ein neues Ende erstellt\).|  
|[CTypedPtrList::GetAt](../Topic/CTypedPtrList::GetAt.md)|Ruft das Element in einer angegebenen Position ab.|  
|[CTypedPtrList::GetHead](../Topic/CTypedPtrList::GetHead.md)|Gibt das Anfangselement der Liste zurück \(kann nicht leer sein\).|  
|[CTypedPtrList::GetNext](../Topic/CTypedPtrList::GetNext.md)|Ruft das folgende Element zum Durchlaufen ab.|  
|[CTypedPtrList::GetPrev](../Topic/CTypedPtrList::GetPrev.md)|Ruft das vorherige Element zum Durchlaufen ab.|  
|[CTypedPtrList::GetTail](../Topic/CTypedPtrList::GetTail.md)|Gibt das Endeelement der Liste zurück \(kann nicht leer sein\).|  
|[CTypedPtrList::RemoveHead](../Topic/CTypedPtrList::RemoveHead.md)|Entfernt das Element aus dem Anfang der Liste.|  
|[CTypedPtrList::RemoveTail](../Topic/CTypedPtrList::RemoveTail.md)|Entfernt das Element aus dem Ende der Liste.|  
|[CTypedPtrList::SetAt](../Topic/CTypedPtrList::SetAt.md)|Legt das Element in einer angegebenen Position fest.|  
  
## Hinweise  
 Wenn Sie `CTypedPtrList` statt `CObList` oder `CPtrList` verwenden, beseitigen die C\+\+\-Typüberprüfungsfunktionshilfen die Fehler, die von nicht übereinstimmende Zeigertypen verursacht werden.  
  
 Darüber hinaus wird der `CTypedPtrList` Wrapper Großteil der Umwandlung aus, die erforderlich wäre, wenn Sie `CObList` oder `CPtrList` haben.  
  
 Da alle `CTypedPtrList`\-Funktionen inline sind, hat Verwendung dieser Vorlage nicht wesentlich die Größe oder die Geschwindigkeit des Codes.  
  
 Die Listen, die von `CObList` abgeleitet werden, können serialisiert werden, aber die, die von `CPtrList` können nicht abgeleitet werden.  
  
 Wenn ein `CTypedPtrList`\-Objekt gelöscht oder wenn seine Elemente entfernt werden, nur die Zeiger entfernt werden, nicht die Entitäten, die darauf verweisen.  
  
 Weitere Informationen zur Verwendung von `CTypedPtrList`, finden Sie in Artikel [Auflistungen](../../mfc/collections.md) und [Auf Vorlagen basierende Klassen](../../mfc/template-based-classes.md).  
  
## Beispiel  
 Dieses Beispiel erstellt eine Instanz von `CTypedPtrList`, fügt ein Objekt hinzu, serialisiert die Liste auf den Datenträger und löscht dann das Objekt:  
  
 [!CODE [NVC_MFCCollections#110](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCCollections#110)]  
  
 [!CODE [NVC_MFCCollections#111](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCCollections#111)]  
  
## Vererbungshierarchie  
 `BASE_CLASS`  
  
 `_CTypedPtrList`  
  
 `CTypedPtrList`  
  
## Anforderungen  
 **Header:**  afxtempl.h  
  
## Siehe auch  
 [MFC\-Beispiel COLLECT](../../top/visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CPtrList Class](../../mfc/reference/cptrlist-class.md)   
 [CObList Class](../../mfc/reference/coblist-class.md)