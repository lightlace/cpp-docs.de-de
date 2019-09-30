---
title: Standarddialogfeld-Klassen
ms.date: 11/04/2016
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
ms.openlocfilehash: d11d0978763d9599b0471a8e994f15a267f7cb8f
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685563"
---
# <a name="common-dialog-classes"></a>Standarddialogfeld-Klassen

Zusätzlich zur [CDialog](../mfc/reference/cdialog-class.md)-Klasse stellt MFC mehrere Klassen bereit, die von `CDialog` abgeleitet werden, die häufig verwendete Dialogfelder Kapseln, wie in der folgenden Tabelle dargestellt. Die gekapselten Dialogfelder werden als "allgemeine Dialogfelder" bezeichnet und sind Teil der allgemeinen Windows-Dialogfeld Bibliothek (kommdlg). DLL). Die Dialogfeld Vorlagen-Ressourcen und der Code für diese Klassen werden in den allgemeinen Windows-Dialogfeldern bereitgestellt, die Teil der Windows-Versionen 3,1 und höher sind.

### <a name="common-dialog-classes"></a>Standarddialogfeld-Klassen

|Abgeleitete Dialogfeld Klasse|Zweck|
|--------------------------|-------------|
|[CColorDialog](../mfc/reference/ccolordialog-class.md)|Ermöglicht Benutzern das Auswählen von Farben.|
|[CFileDialog](../mfc/reference/cfiledialog-class.md)|Ermöglicht Benutzern das Auswählen eines Datei namens, der geöffnet oder gespeichert werden soll.|
|[CFindReplaceDialog](../mfc/reference/cfindreplacedialog-class.md)|Ermöglicht Benutzern das Initiieren eines Such-oder Ersetzungs Vorgangs in einer Textdatei.|
|[CFontDialog](../mfc/reference/cfontdialog-class.md)|Ermöglicht Benutzern das Angeben einer Schriftart.|
|[CPrintDialog](../mfc/reference/cprintdialog-class.md)|Ermöglicht Benutzern das Angeben von Informationen für einen Druckauftrag.|
|[CPrintDialogEx](../mfc/reference/cprintdialogex-class.md)|Eigenschaften Blatt für Windows-Druck.|

Weitere Informationen zu den allgemeinen Dialog Klassen finden Sie unter den einzelnen Klassennamen in der *MFC-Referenz*. MFC bietet auch eine Reihe von Standarddialog Klassen, die für OLE verwendet werden. Weitere Informationen zu diesen Klassen finden Sie in der *MFC-Referenz*in der Basisklasse [COleDialog](../mfc/reference/coledialog-class.md).

Drei andere Klassen in MFC verfügen über Dialog ähnliche Merkmale. Informationen zu den Klassen [CFormView](../mfc/reference/cformview-class.md), [CRecordView](../mfc/reference/crecordview-class.md)und [CDaoRecordView](../mfc/reference/cdaorecordview-class.md)finden Sie in den Klassen in der *MFC-Referenz*. Weitere Informationen über die [CDialogBar](../mfc/reference/cdialogbar-class.md)-Klasse finden Sie unter [Dialog leisten](../mfc/dialog-bars.md).

## <a name="see-also"></a>Siehe auch

[Dialogfelder](../mfc/dialog-boxes.md)<br/>
[Arbeiten mit Dialog Feldern in MFC](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[Dialogfelder in OLE](../mfc/dialog-boxes-in-ole.md)
