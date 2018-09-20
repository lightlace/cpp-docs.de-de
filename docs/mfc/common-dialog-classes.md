---
title: Standarddialogfeld-Klassen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0a937ded9fe356627e36ad0262e749446553aa91
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46379722"
---
# <a name="common-dialog-classes"></a>Standarddialogfeld-Klassen

Zusätzlich zur Klasse [CDialog](../mfc/reference/cdialog-class.md), MFC stellt mehrere Klassen, die von `CDialog` , häufig verwendete Dialogfelder kapseln, wie in der folgenden Tabelle gezeigt. Diese Dialogfelder werden als "Allgemeine Dialogfelder" bezeichnet und sind Teil der Windows-allgemeinen Dialogfeld Bibliothek (COMMDLG. (DLL). Die Dialogfeld-Vorlagenressourcen und den Code für diese Klassen werden in der Windows Standarddialogfelder bereitgestellt, die Teil der Windows-Versionen 3.1 und höher.

### <a name="common-dialog-classes"></a>Standarddialogfeld-Klassen

|Abgeleitete Dialogfeldklassen|Zweck|
|--------------------------|-------------|
|[CColorDialog](../mfc/reference/ccolordialog-class.md)|Können Benutzer wählen Farben an.|
|[CFileDialog](../mfc/reference/cfiledialog-class.md)|Können Benutzer entscheiden, einen Dateinamen zu öffnen oder zu speichern.|
|[CFindReplaceDialog](../mfc/reference/cfindreplacedialog-class.md)|Ermöglicht Benutzer initiiert eine Suche oder Ersetzungsvorgangs in einer Textdatei.|
|[CFontDialog](../mfc/reference/cfontdialog-class.md)|Ermöglicht Benutzer, die eine Schriftart angeben.|
|[CPrintDialog](../mfc/reference/cprintdialog-class.md)|Ermöglicht Benutzer, die Informationen für einen Druckauftrag angeben.|
|[CPrintDialogEx](../mfc/reference/cprintdialogex-class.md)|Windows-druckeigenschaftenblatt.|

Weitere Informationen über das Standarddialogfeld-Klassen finden Sie unter den einzelnen Klassennamen in der *MFC-Referenz*. MFC bietet auch eine Reihe von Standarddialogfeld-Klassen, die für OLE verwendet. Informationen zu diesen Klassen finden Sie die Basisklasse, [COleDialog](../mfc/reference/coledialog-class.md)in die *MFC-Referenz*.

Drei weitere Klassen in MFC über die Dialogfeld-ähnliche Merkmale verfügen. Informationen zu Klassen [CFormView](../mfc/reference/cformview-class.md), [CRecordView](../mfc/reference/crecordview-class.md), und [CDaoRecordView](../mfc/reference/cdaorecordview-class.md), finden Sie unter den Klassen in der *MFC-Referenz*. Informationen zur Klasse [CDialogBar](../mfc/reference/cdialogbar-class.md), finden Sie unter [Dialogleisten](../mfc/dialog-bars.md).

## <a name="see-also"></a>Siehe auch

[Dialogfelder](../mfc/dialog-boxes.md)<br/>
[Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[Dialogfelder in OLE](../mfc/dialog-boxes-in-ole.md)

