---
title: "CPtrList Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CPtrList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPtrList class"
  - "generic lists"
  - "Listen, generic"
ms.assetid: 4139a09c-4338-4f42-9eea-51336120b43c
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CPtrList Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unterstützt Listen void\-Zeigern.  
  
## Syntax  
  
```  
class CPtrList : public CObject  
```  
  
## Member  
 Die Memberfunktionen von `CPtrList` entsprechen den Memberfunktionen der [CObList](../../mfc/reference/coblist-class.md)\-Klasse.  Aufgrund dieser Ähnlichkeit können Sie die `CObList`\-Referenzdokumentation für Memberfunktionsbesonderheiten verwenden.  Wenn Sie einen `CObject`\-Zeiger als Funktionsparameter oder als Rückgabewert finden, ersetzen Sie einen Zeiger auf `void`.  
  
 `CObject*& CObList::GetHead() const;`  
  
 Beispielsweise übersetzt zu  
  
 `void*& CPtrList::GetHead() const;`  
  
## Hinweise  
 `CPtrList` enthält das `IMPLEMENT_DYNAMIC`\-Makro zur Unterstützung von Laufzeittypenzugriff und zum Sichern in ein `CDumpContext`\-Objekt.  Wenn Sie eine Sicherung einzelner Zeigerlistenelemente benötigen, müssen Sie die Tiefe des Sicherungskontexts auf 1 oder größer festlegen.  
  
 Zeigerlisten können nicht serialisiert werden.  
  
 Wenn ein `CPtrList`\-Objekt gelöscht wird oder dessen Elemente entfernt werden, werden nur die Zeiger, und nicht die Entitäten, auf die sie verweisen, entfernt.  
  
 Weitere Informationen zum Verwenden von `CPtrList` finden Sie im Artikel [Auflistungen](../../mfc/collections.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CPtrList`  
  
## Anforderungen  
 **Header:** afxcoll.h  
  
## Siehe auch  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CObList Class](../../mfc/reference/coblist-class.md)