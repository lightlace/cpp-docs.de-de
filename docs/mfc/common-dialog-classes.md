---
title: Allgemeine Dialogfeldklassen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- dialog classes [MFC]
- dialog boxes [MFC], Windows common dialogs
- common dialog boxes [MFC], common dialog classes
- common dialog classes [MFC]
- MFC dialog boxes [MFC], Windows common dialogs
- Windows common dialogs [MFC]
- dialog classes [MFC], common
- common dialog boxes [MFC]
ms.assetid: 5c4f6443-896c-4b05-a7df-8169fdadc71d
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 50adbc6faa802802c36e18c614992341def06331
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="common-dialog-classes"></a>Standarddialogfeld-Klassen
Zusätzlich zur Klasse [CDialog](../mfc/reference/cdialog-class.md), MFC stellt mehrere Klassen abgeleitet `CDialog` , häufig verwendete Dialogfelder kapseln, wie in der folgenden Tabelle gezeigt. Diese Dialogfelder werden als "häufig verwendete Dialogfelder" bezeichnet und sind Teil der Windows-allgemeine Dialogfeld Bibliothek (COMMDLG. (DLL). Der Dialogfeld-Vorlagenressourcen und den Code für diese Klassen werden in den Fenstern häufig verwendete Dialogfelder bereitgestellt, die Teil von Windows-Versionen 3.1 und höher sind.  
  
### <a name="common-dialog-classes"></a>Standarddialogfeld-Klassen  
  
|Abgeleitete Dialogfeldklassen|Zweck|  
|--------------------------|-------------|  
|[CColorDialog](../mfc/reference/ccolordialog-class.md)|Können Benutzer wählen Farben an.|  
|[CFileDialog](../mfc/reference/cfiledialog-class.md)|Ermöglicht Benutzer wählen Sie einen Dateinamen zu öffnen oder zu speichern.|  
|[CFindReplaceDialog](../mfc/reference/cfindreplacedialog-class.md)|Ermöglicht Benutzer das Initiieren einer Suche oder Ersetzungsvorgangs in einer Textdatei.|  
|[CFontDialog](../mfc/reference/cfontdialog-class.md)|Können Benutzer eine Schriftart angeben.|  
|[CPrintDialog](../mfc/reference/cprintdialog-class.md)|Ermöglicht Benutzer, die Informationen für einen Druckauftrag angeben.|  
|[CPrintDialogEx](../mfc/reference/cprintdialogex-class.md)|Windows 2000-Eigenschaftenblatt Drucken.|  
  
 Weitere Informationen über das Standarddialogfeld-Klassen finden Sie unter den einzelnen Klassennamen in der *MFC-Referenz*. MFC bietet auch eine Reihe von Standarddialogfeld-Klassen, die für OLE verwendet. Informationen zu diesen Klassen finden Sie unter der Basisklasse [COleDialog](../mfc/reference/coledialog-class.md)in der *MFC-Referenz*.  
  
 Drei andere Klassen in MFC über Dialogfeld-ähnliche Merkmale verfügen. Informationen zu Klassen [CFormView](../mfc/reference/cformview-class.md), [CRecordView](../mfc/reference/crecordview-class.md), und [CDaoRecordView](../mfc/reference/cdaorecordview-class.md), finden Sie in der Klassen in der *MFC-Referenz*. Informationen zur Klasse [CDialogBar](../mfc/reference/cdialogbar-class.md), finden Sie unter [Dialogleisten](../mfc/dialog-bars.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Dialogfelder](../mfc/dialog-boxes.md)   
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)   
 [Dialogfelder in OLE](../mfc/dialog-boxes-in-ole.md)

