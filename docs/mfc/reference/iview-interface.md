---
title: "IView Interface"
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
  - "IView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IView class"
  - "views [MFC]"
  - "Ansichten, Klassen"
ms.assetid: 9321f299-486e-4551-bee9-d2c4a7b91548
caps.latest.revision: 23
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# IView Interface
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert mehrere Möglichkeiten, die [CWinFormsView](../../mfc/reference/cwinformsview-class.md) verwendet, Ansichtsbenachrichtigungen zu einem verwalteten Steuerelement zu senden.  
  
## Syntax  
  
```  
interface class IView  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[IView::OnActivateView](../Topic/IView::OnActivateView.md)|Aufgerufen von MFC, wenn eine Ansicht aktiviert oder deaktiviert ist.|  
|[IView::OnInitialUpdate](../Topic/IView::OnInitialUpdate.md)|Aufgerufen vom Framework, nachdem die erste Ansicht zum Dokument angefügt wurde, jedoch bevor die Ansicht zuerst angezeigt wird.|  
|[IView::OnUpdate](../Topic/IView::OnUpdate.md)|Aufgerufen von MFC, nachdem das Dokument der Ansicht geändert wurde, Diese Funktion kann der Ansicht, um die Anzeige zu aktualisieren, um Änderungen wiederzugeben.|  
  
## Hinweise  
 `IView` implementiert verschiedene Methoden, die `CWinFormsView` Verwendung, allgemeine Ansichtsbenachrichtigungen zu einem gehosteten Steuerelement verwalteten weiterzuleiten.  Diese sind [OnInitialUpdate](../Topic/IView::OnInitialUpdate.md), [OnUpdate](../Topic/IView::OnUpdate.md) und [OnActivateView](../Topic/IView::OnActivateView.md).  
  
 `IView` ist zu [CView](../../mfc/reference/cview-class.md) ähnlich, wird jedoch nur mit verwalteten Ansichten und Steuerelemente verwendet.  
  
 Weitere Informationen zur Verwendung von Windows Forms, finden Sie unter [Verwenden eines Windows Form\-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
## Anforderungen  
 Header: afxwinforms.h \(definiert in Assembly in \\ atlmfc \\ lib mfcmifc80.dll\)  
  
## Siehe auch  
 [CWinFormsView Class](../../mfc/reference/cwinformsview-class.md)   
 [CView Class](../../mfc/reference/cview-class.md)