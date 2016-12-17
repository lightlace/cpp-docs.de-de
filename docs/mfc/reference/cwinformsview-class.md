---
title: "CWinFormsView Class"
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
  - "CWinFormsView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWinFormsView class"
  - "MFC [C++], Windows Forms-Unterstützung"
  - "Windows Forms [C++], MFC-Unterstützung"
ms.assetid: d597e397-6529-469b-88f5-7f65a6b9e895
caps.latest.revision: 26
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# CWinFormsView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt generische Funktionen zum Hosten eines Windows Forms\-Steuerelements als MFC\-Ansicht bereit.  
  
## Syntax  
  
```  
class CWinFormsView : public CView;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CWinFormsView::CWinFormsView](../Topic/CWinFormsView::CWinFormsView.md)|Erstellt ein `CWinFormsView`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CWinFormsView::GetControl](../Topic/CWinFormsView::GetControl.md)|Ruft einen Zeiger auf das Windows Forms\-Steuerelement ab.|  
  
### Öffentliche Operatoren  
  
|Name||  
|----------|-|  
|[CWinFormsView::operator Control^](../Topic/CWinFormsView::operator%20Control%5E.md)|Wandelt einen Typ als Zeiger auf einem Windows Forms\-Steuerelement um.|  
  
## Hinweise  
 MFC verwendet die `CWinFormsView`\-Klasse, um eine .NET Framework\-WindowsForms\-Steuerelement innerhalb einer MFC\-Ansicht zu hosten.  Das Steuerelement ist ein untergeordnetes Element der systemeigenen Ansicht und nimmt den gesamten Clientbereich der MFC\-Ansicht.  Das Ergebnis ist einer `CFormView` ähneln und ermöglicht es Ihnen, den Windows Forms\-Designer und die Laufzeit zu nutzen, umfangreiche formularbasierte Ansichten zu erstellen.  
  
 Weitere Informationen zur Verwendung von Windows Forms, finden Sie unter [Verwenden eines Windows Form\-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
> [!NOTE]
>  Windows Forms\-Integration funktioniert nur in Projekten, die dynamisch mit MFC verknüpft sind \(Projekte, in denen AFXDLL definiert ist\).  
  
> [!NOTE]
>  CWinFormsView unterstützt nicht das MFC\-Splitterfenster \([CSplitterWnd Class](../../mfc/reference/csplitterwnd-class.md)\).  Derzeit nur das Windows Form\-Splitter\-Steuerelement \(<xref:System.Windows.Forms.Splitter>\) wird unterstützt.  
  
## Anforderungen  
 **Header:** afxwinforms.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CWinFormsControl Class](../../mfc/reference/cwinformscontrol-class.md)   
 [CWinFormsDialog Class](../../mfc/reference/cwinformsdialog-class.md)   
 [CFormView Class](../../mfc/reference/cformview-class.md)