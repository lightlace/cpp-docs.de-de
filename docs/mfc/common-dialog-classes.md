---
title: "Standarddialogfeld-Klassen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Allgemeine Dialogfelder [C++]"
  - "Allgemeine Dialogfelder [C++], Allgemeine Dialogfeldklassen"
  - "Allgemeine Dialogfeldklassen [C++]"
  - "Dialogfelder [C++], Windows (allgemeine Dialoge)"
  - "Dialogklassen [C++]"
  - "Dialogklassen [C++], Allgemein"
  - "MFC-Dialogfelder, Windows (allgemeine Dialoge)"
  - "Windows (allgemeine Dialoge) [C++]"
ms.assetid: 5c4f6443-896c-4b05-a7df-8169fdadc71d
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Standarddialogfeld-Klassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Neben der Klasse [CDialog\-Klasse](../mfc/reference/cdialog-class.md), MFC stellt mehrere Klassen bereit, die von `CDialog` abgeleitet werden, die häufig verwendete Dialogfelder, kapseln, wie in der folgenden Tabelle.  Die Encapsulated Dialogfelder werden die "Standarddialogfelder" bezeichnet und sind Bestandteil der allgemeinen Dialogfeldbibliothek Windows \(COMMDLG.DLL\).  Die Dialogfeldvorlagenressourcen und Code für diese Klassen werden in den Windows\-häufigverwendetes Dialogfeld bereitgestellt, die Teil Windows\-Versionen 3.1 und höher sind.  
  
### Allgemeine Dialogfeldklassen  
  
|Abgeleitete Dialogfeldklasse|Zweck|  
|----------------------------------|-----------|  
|[CColorDialog](../mfc/reference/ccolordialog-class.md)|Ermöglicht Farben des Benutzers.|  
|[CFileDialog](../mfc/reference/cfiledialog-class.md)|Ermöglicht Benutzern einen Dateinamen auswählen, um diese zu öffnen oder zu speichern.|  
|[CFindReplaceDialog](../mfc/reference/cfindreplacedialog-class.md)|Ermöglicht Benutzern eine Suche oder einen Ersetzungsvorgang in einer Textdatei initiieren.|  
|[CFontDialog](../mfc/reference/cfontdialog-class.md)|Ermöglicht Benutzern eine Schriftart angeben.|  
|[CPrintDialog](../mfc/reference/cprintdialog-class.md)|Ermöglicht Benutzern Informationen für einen Druckauftrag angeben.|  
|[CPrintDialogEx](../mfc/reference/cprintdialogex-class.md)|Windows 2000\-Druckeigenschaftenblatt.|  
  
 Weitere Informationen über die allgemeinen Dialogfeldklassen, finden Sie die einzelnen Klassennamen in der *MFC\-Referenz*.  MFC stellt auch verschiedene Standarddialogfeldklassen bereit, die für OLE verwendet werden.  Informationen über diese Klassen, finden Sie die Basisklasse, [COleDialog](../mfc/reference/coledialog-class.md), in der *MFC\-Referenz*.  
  
 Drei andere Klassen in MFC Dialogfeld haben ähnliche Merkmale.  Informationen zu Klassen finden [CFormView](../mfc/reference/cformview-class.md), [CRecordView](../mfc/reference/crecordview-class.md) und [CDaoRecordView](../mfc/reference/cdaorecordview-class.md), die Klassen in der *MFC\-Referenz*.  Informationen über die Klassen [CDialogBar](../mfc/reference/cdialogbar-class.md), finden Sie unter [Dialogleisten](../mfc/dialog-bars.md).  
  
## Siehe auch  
 [Dialogfelder](../mfc/dialog-boxes.md)   
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)   
 [Dialogfelder in OLE](../mfc/dialog-boxes-in-ole.md)