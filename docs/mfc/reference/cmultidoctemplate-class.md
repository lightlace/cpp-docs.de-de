---
title: "CMultiDocTemplate Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMultiDocTemplate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMultiDocTemplate class"
  - "MDI, Vorlage"
ms.assetid: 5b8aa328-e461-41d0-b388-00594535e119
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CMultiDocTemplate Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Definiert eine Normal\-Vorlage, die das \(Multiple Document Interface\) implementiert.  
  
## Syntax  
  
```  
  
class CMultiDocTemplate : public CDocTemplate  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMultiDocTemplate::CMultiDocTemplate](../Topic/CMultiDocTemplate::CMultiDocTemplate.md)|Erstellt ein `CMultiDocTemplate`\-Objekt.|  
  
## Hinweise  
 Eine MDI\-Anwendung verwendet das Hauptrahmenfenster als Arbeitsbereich, in dem der Benutzer null oder mehr Dokumentrahmenfenster öffnen kann, von denen jedes ein Dokument anzeigt.  Eine ausführlichere Beschreibung des MDI, finden Sie unter *Windows\-Oberflächen\-Richtlinien für Softwareentwurf*.  
  
 Eine Normal\-Vorlage definiert die Beziehungen zwischen drei Typen Klassen:  
  
-   Eine Dokumentklasse, die Sie von [CDocument](../../mfc/reference/cdocument-class.md) berechnen.  
  
-   Eine Ansichtsklasse, die Daten aus der Dokumentklasse anzeigt, lässt oben auf.  Sie können diese Klasse von [CView](../../mfc/reference/cview-class.md), von `CScrollView`, von `CFormView` oder von `CEditView` berechnen.  \(Sie können `CEditView` auch direkt verwenden.\)  
  
-   Eine Rahmenfensterklasse, die die Ansicht enthält.  Eine MDI\-Dokumentvorlage können Sie diese Klasse von `CMDIChildWnd` berechnen, oder, wenn Sie nicht erforderlich ist, um das Verhalten der Dokumentrahmenfenster anzupassen, können Sie [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) direkt verwenden, ohne eine eigene Klasse zu berechnen.  
  
 Eine MDI\-Anwendung kann mehr als einen Typ Dokument unterstützen, und Dokumente verschiedener Typen können gleichzeitig geöffnet sein.  Die Anwendung verfügt über eine Normal\-Vorlage für jeden Dokumenttyp, den sie unterstützt.  Wenn die MDI\-Anwendung Arbeitsblätter und Textdokumente unterstützt, kann die Anwendung zwei `CMultiDocTemplate`\-Objekte.  
  
 Die Anwendung verwendet die Normal\-Vorlage, wenn der Benutzer ein neues Dokument erstellt.  Wenn die Anwendung mehr als einen Typ Dokument unterstützt, ruft das Framework die Namen der unterstützten Dokumenttypen von Dokumentvorlagen ab und in einer Liste im neuen Dialogfeld Datei an.  Sobald der Benutzer einen Dokumenttyp ausgewählt hat, erstellt die Anwendung ein Dokumentklassenobjekt, ein Rahmenfensterobjekt und ein Ansichtsobjekt und fügt sie miteinander an.  
  
 Sie müssen, um keine Memberfunktionen von `CMultiDocTemplate` außer den Konstruktor aufzurufen.  Das Framework behandelt `CMultiDocTemplate`\-Objekte intern.  
  
 Weitere Informationen zu `CMultiDocTemplate`, finden Sie unter [Dokumentvorlagen und der Dokument\/Ansichts\-Erstellungs\-Prozess](../../mfc/document-templates-and-the-document-view-creation-process.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md)  
  
 `CMultiDocTemplate`  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [CDocTemplate Class](../../mfc/reference/cdoctemplate-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDocTemplate Class](../../mfc/reference/cdoctemplate-class.md)   
 [CSingleDocTemplate Class](../../mfc/reference/csingledoctemplate-class.md)   
 [CWinApp Class](../../mfc/reference/cwinapp-class.md)