---
title: "CHtmlEditCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CHtmlEditCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHtmlEditCtrl class"
ms.assetid: 0fc4a238-b05f-4874-9edc-6a6701f064d9
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CHtmlEditCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt die Funktionalität des ActiveX\-Steuerelement browseractivex\-steuerelements in einem MFC\-Fenster bereit.  
  
## Syntax  
  
```  
class CHtmlEditCtrl: public CWnd,   
   public CHtmlEditCtrlBase< CHtmlEditCtrl >  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CHtmlEditCtrl::CHtmlEditCtrl](../Topic/CHtmlEditCtrl::CHtmlEditCtrl.md)|Erstellt ein `CHtmlEditCtrl`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CHtmlEditCtrl::Create](../Topic/CHtmlEditCtrl::Create.md)|Erstellt ein ActiveX\-Steuerelement browseractivex\-steuerelement und fügt es dem `CHtmlEditCtrl`\-Objekt.  Diese Funktion wird automatisch das ActiveX\-Steuerelement browseractivex\-steuerelement in den Bearbeitungsmodus.|  
|[CHtmlEditCtrl::GetDHtmlDocument](../Topic/CHtmlEditCtrl::GetDHtmlDocument.md)|Ruft die [IHTMLDocument2](https://msdn.microsoft.com/en-us/library/aa752574.aspx)\-Schnittstelle im Dokument ab, die im enthaltenden ActiveX\-Steuerelement browsersteuerelement geladen wird.|  
|[CHtmlEditCtrl::GetStartDocument](../Topic/CHtmlEditCtrl::GetStartDocument.md)|Ruft die URL zu einem Standarddokument ab, um im enthaltenden ActiveX\-Steuerelement browsersteuerelement zu laden.|  
  
## Hinweise  
 Das gehostete ActiveX\-Steuerelement browsersteuerelement wird automatisch in den Bearbeitungsmodus gesetzt, nachdem es erstellt wurde.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CHtmlEditCtrlBase](../../mfc/reference/chtmleditctrlbase-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CHtmlEditCtrl`  
  
## Anforderungen  
 **Header:** afxhtml.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)