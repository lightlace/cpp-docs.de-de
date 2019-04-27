---
title: Erstellen und Anzeigen von Dialogfeldern
ms.date: 11/04/2016
helpviewer_keywords:
- modal dialog boxes [MFC], creating
- opening dialog boxes
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], displaying
ms.assetid: 1c5219ee-8b46-44bc-9708-83705d4f248b
ms.openlocfilehash: e0b7ff31576b345ac2911e62a6e10469845eecba
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62175029"
---
# <a name="creating-and-displaying-dialog-boxes"></a>Erstellen und Anzeigen von Dialogfeldern

Erstellen ein-Objekt eines Dialogfelds ist ein zweistufiger Prozess. Zunächst erstellen Sie das Dialogfeldobjekt, und erstellen Sie dann das Dialogfeld. Modale und nicht modale Dialogfelder unterscheiden sich leicht in der Vorgehensweise zum Erstellen und diese anzeigen. Die folgende Tabelle enthält wie modale und nicht modale Dialogfeld Felder normalerweise erstellt und angezeigt werden.

### <a name="dialog-creation"></a>Dialogfeld-Erstellung

|Dialogfeldtyp|Zum Erstellen|
|-----------------|----------------------|
|[Ohne Modus](../mfc/creating-modeless-dialog-boxes.md)|Erstellen Sie `CDialog`, rufen Sie anschließend `Create` Member-Funktion.|
|[Modal](../mfc/creating-modal-dialog-boxes.md)|Erstellen Sie `CDialog`, rufen Sie anschließend `DoModal` Member-Funktion.|

Sie können, wenn Sie möchten, erstellen das Dialogfeld aus einer [Dialogfeldvorlage im Speicher](../mfc/using-a-dialog-template-in-memory.md) , den Sie erstellt haben und nicht aus einer Dialogfeldvorlagen-Ressource. Dies ist jedoch ein Thema für fortgeschrittene.

## <a name="see-also"></a>Siehe auch

[Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)
