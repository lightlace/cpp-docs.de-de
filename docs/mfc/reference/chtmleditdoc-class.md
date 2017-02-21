---
title: "CHtmlEditDoc Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CHtmlEditDoc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHtmlEditDoc class"
ms.assetid: b2cca61f-e5d6-4099-b0d1-46bf85f0bd64
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CHtmlEditDoc Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mit [CHtmlEditView](../../mfc/reference/chtmleditview-class.md) stellt die Funktionalität der ActiveX\-Steuerelement browserbearbeitungsplattform im Kontext der MFC\-Dokument\-\/Ansichtarchitektur bereit.  
  
## Syntax  
  
```  
class AFX_NOVTABLE CHtmlEditDoc : public CDocument  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CHtmlEditDoc::CHtmlEditDoc](../Topic/CHtmlEditDoc::CHtmlEditDoc.md)|Erstellt ein `CHtmlEditDoc`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CHtmlEditDoc::GetView](../Topic/CHtmlEditDoc::GetView.md)|Ruft das `CHtmlEditView`\-Objekt ab, das diesem Dokument angefügt wird.|  
|[CHtmlEditDoc::IsModified](../Topic/CHtmlEditDoc::IsModified.md)|Gibt zurück, ob das zugeordnete ActiveX\-Steuerelement browsersteuerelement der Ansicht ein Dokument enthält, das vom Benutzer geändert wurde.|  
|[CHtmlEditDoc::OpenURL](../Topic/CHtmlEditDoc::OpenURL.md)|Öffnet eine URL.|  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 `CHtmlEditDoc`  
  
## Anforderungen  
 **Header:** afxhtml.h  
  
## Siehe auch  
 [HTMLEdit\-Beispiel](../../top/visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)