---
title: "CMFCImageEditorDialog Class"
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
  - "CMFCImageEditorDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCImageEditorDialog class"
ms.assetid: 6a7d08f3-1ec2-4062-9b79-a0c2776b58d1
caps.latest.revision: 24
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCImageEditorDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CMFCImageEditorDialog`\-Klasse unterstützt ein Bildbearbeitungsdialogfeld.  
  
## Syntax  
  
```  
class CMFCImageEditorDialog : public CDialogEx  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCImageEditorDialog::CMFCImageEditorDialog](../Topic/CMFCImageEditorDialog::CMFCImageEditorDialog.md)|Erstellt ein `CMFCImageEditorDialog`\-Objekt.|  
  
## Hinweise  
 Die Klasse stellt `CMFCImageEditorDialog` ein Dialogfeld, das einschließt:  
  
-   Ein Bildbereich, den Sie verwenden, um einzelne Pixel in ein Bild zu ändern.  
  
-   Zeichentools, um die Pixel des Bildbereichs zu ändern.  
  
-   Eine Farbpalette, um die Farbe anzugeben, die von der Zeichentools verwendet wird.  
  
-   Ein Vorschaubereich, der die Auswirkungen der Bearbeitung anzeigt.  
  
 Die folgende Abbildung zeigt ein Bildbearbeitungsdialogfeld an.  
  
 ![CMFCImageEditorDialog&#45;Dialogfeld](../../mfc/reference/media/imageedit.png "ImageEdit")  
  
 Eine Möglichkeit, ein Objekt `CMFCImageEditorDialog` zu verwenden ist, sie zu übergeben ein bearbeitet werden `CBitmap` Bild.  Erstellen Sie kein großes Bild, da der Imagebearbeitungsbereich einer eingeschränkten Größe hat und die logische Pixelgröße angepasst wird, um den Bereich zu passen.  Rufen Sie die `DoModal`\-Methode, um ein modales Dialogfeld zu starten.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog\-Klasse](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCImageEditorDialog](../../mfc/reference/cmfcimageeditordialog-class.md)  
  
## Anforderungen  
 **Header:** afximageeditordialog.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)