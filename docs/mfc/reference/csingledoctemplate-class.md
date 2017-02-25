---
title: "CSingleDocTemplate Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSingleDocTemplate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSingleDocTemplate class"
  - "Dokumentvorlagen, single"
  - "Einzeldokumentoberfläche (SDI), Anwendungen"
  - "Vorlagen, SDI"
ms.assetid: 4f3a8212-81ee-48a0-ad22-e0ed7c36a391
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CSingleDocTemplate Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Definiert eine Normal\-Vorlage, die das eine SDI \(Single Document Interface\) implementiert.  
  
## Syntax  
  
```  
class CSingleDocTemplate : public CDocTemplate  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CSingleDocTemplate::CSingleDocTemplate](../Topic/CSingleDocTemplate::CSingleDocTemplate.md)|Erstellt ein `CSingleDocTemplate`\-Objekt.|  
  
## Hinweise  
 Eine SDI\-Anwendung verwendet das Hauptrahmenfenster, um ein Dokument anzuzeigen; nur ein Dokument kann gleichzeitig geöffnet sein.  
  
 Eine Normal\-Vorlage definiert die Beziehung zwischen drei Typen Klassen:  
  
-   Eine Dokumentklasse, die Sie von **CDocument** berechnen.  
  
-   Eine Ansichtsklasse, die Daten aus der Dokumentklasse anzeigt, lässt oben auf.  Sie können diese Klasse von `CView`, von `CScrollView`, von `CFormView` oder von `CEditView` berechnen.  \(Sie können `CEditView` auch direkt verwenden.\)  
  
-   Eine Rahmenfensterklasse, die die Ansicht enthält.  Eine SDI\-Dokumentvorlage können Sie diese Klasse von abgeleitet, `CFrameWnd` Wenn Sie nicht erforderlich ist, um das Verhalten des Hauptrahmenfensters anzupassen, können Sie `CFrameWnd` direkt verwenden, ohne eine eigene Klasse zu berechnen.  
  
 Eine SDI\-Anwendung unterstützt in der Regel einen Typ Dokument, enthält sie nur ein `CSingleDocTemplate`\-Objekt.  Nur ein Dokument kann gleichzeitig geöffnet sein.  
  
 Sie müssen, um keine Memberfunktionen von `CSingleDocTemplate` außer den Konstruktor aufzurufen.  Das Framework behandelt `CSingleDocTemplate`\-Objekte intern.  
  
 Weitere Informationen zur Verwendung von `CSingleDocTemplate`, finden Sie unter [Dokumentvorlagen und der Dokument\/Ansichts\-Erstellungs\-Prozess](../../mfc/document-templates-and-the-document-view-creation-process.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md)  
  
 `CSingleDocTemplate`  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [MFC\-Beispiel DOCKTOOL](../../top/visual-cpp-samples.md)   
 [CDocTemplate Class](../../mfc/reference/cdoctemplate-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDocTemplate Class](../../mfc/reference/cdoctemplate-class.md)   
 [CDocument Class](../../mfc/reference/cdocument-class.md)   
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)   
 [CMultiDocTemplate Class](../../mfc/reference/cmultidoctemplate-class.md)   
 [CView Class](../../mfc/reference/cview-class.md)   
 [CWinApp Class](../../mfc/reference/cwinapp-class.md)