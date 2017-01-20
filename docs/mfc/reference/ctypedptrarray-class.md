---
title: "CTypedPtrArray Class"
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
  - "CTypedPtrArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTypedPtrArray class"
  - "pointer arrays"
ms.assetid: e3ecdf1a-a889-4156-92dd-ddbd36ccd919
caps.latest.revision: 22
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# CTypedPtrArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt einen typsicheren "Wrapper" für Objekte der Klasse `CPtrArray` oder `CObArray` bereit.  
  
## Syntax  
  
```  
template< class BASE_CLASS, class TYPE >  
class CTypedPtrArray : public BASE_CLASS  
```  
  
#### Parameter  
 `BASE_CLASS`  
 Basisklasse der typisierten Zeigerarrayklasse; muss eine Array\-Klasse \(`CObArray` oder `CPtrArray`\).  
  
 `TYPE`  
 Typ der Elemente im Basisklassenarray gespeichert.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CTypedPtrArray::Add](../Topic/CTypedPtrArray::Add.md)|Fügt ein neues Element am Ende eines Arrays hinzu.  Wächst das Array ggf.|  
|[CTypedPtrArray::Append](../Topic/CTypedPtrArray::Append.md)|Fügt den Inhalt von einem Array Ende von anderen hinzu.  Wächst das Array ggf.|  
|[CTypedPtrArray::Copy](../Topic/CTypedPtrArray::Copy.md)|Kopiert ein anderes Array dem Array; vergrößert das Array.|  
|[CTypedPtrArray::ElementAt](../Topic/CTypedPtrArray::ElementAt.md)|Gibt einen temporären Verweis auf das Element innerhalb des Arrays zurück.|  
|[CTypedPtrArray::GetAt](../Topic/CTypedPtrArray::GetAt.md)|Gibt den Wert an einem angegebenen Index zurück.|  
|[CTypedPtrArray::InsertAt](../Topic/CTypedPtrArray::InsertAt.md)|Fügt ein Element \(oder alle Elemente in anderen Array\) zu einem angegebenen Index ein.|  
|[CTypedPtrArray::SetAt](../Topic/CTypedPtrArray::SetAt.md)|Legt den Wert für einen angegebenen Index fest; Array nicht zulässig, um vergrößert.|  
|[CTypedPtrArray::SetAtGrow](../Topic/CTypedPtrArray::SetAtGrow.md)|Legt den Wert für einen angegebenen Index fest; vergrößert das Array.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CTypedPtrArray::operator](../Topic/CTypedPtrArray::operator.md)|Legt fest oder ruft das Element am angegebenen Index ab.|  
  
## Hinweise  
 Wenn Sie `CTypedPtrArray` statt `CPtrArray` oder `CObArray` verwenden, beseitigen die C\+\+\-Typüberprüfungsfunktionshilfen die Fehler, die von nicht übereinstimmende Zeigertypen verursacht werden.  
  
 Darüber hinaus wird der `CTypedPtrArray` Wrapper Großteil der Umwandlung aus, die erforderlich wäre, wenn Sie `CObArray` oder `CPtrArray` haben.  
  
 Da alle `CTypedPtrArray`\-Funktionen inline sind, hat Verwendung dieser Vorlage nicht wesentlich die Größe oder die Geschwindigkeit des Codes.  
  
 Weitere Informationen zur Verwendung von `CTypedPtrArray`, finden Sie in Artikel [Auflistungen](../../mfc/collections.md) und [Auf Vorlagen basierende Klassen](../../mfc/template-based-classes.md).  
  
## Vererbungshierarchie  
 `BASE_CLASS`  
  
 `CTypedPtrArray`  
  
## Anforderungen  
 **Header:**  afxtempl.h  
  
## Siehe auch  
 [MFC\-Beispiel COLLECT](../../top/visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CPtrArray Class](../../mfc/reference/cptrarray-class.md)   
 [CObArray Class](../../mfc/reference/cobarray-class.md)