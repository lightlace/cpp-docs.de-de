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
ms.openlocfilehash: 6d23e4d2c9249ce248eb8092963036f2ba5cacac
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685744"
---
# <a name="creating-and-displaying-dialog-boxes"></a>Erstellen und Anzeigen von Dialogfeldern

Das Erstellen eines Dialog Objekts ist ein zweistufiges Vorgang. Erstellen Sie zuerst das Dialogfeld Objekt, und erstellen Sie dann das Dialogfeld. Modale und nicht modale Dialogfelder unterscheiden sich etwas in dem Prozess, der zum Erstellen und Anzeigen verwendet wurde. In der folgenden Tabelle ist aufgelistet, wie modale und nicht modale Dialogfelder normalerweise erstellt und angezeigt werden.

### <a name="dialog-creation"></a>Dialog Erstellung

|Dialog Feld-Typ|Erstellen|
|-----------------|----------------------|
|[Nicht modales](../mfc/creating-modeless-dialog-boxes.md)|Erstellen Sie `CDialog`, und nennen Sie dann `Create`-Member-Funktion.|
|[Aufkommen](../mfc/creating-modal-dialog-boxes.md)|Erstellen Sie `CDialog`, und nennen Sie dann `DoModal`-Member-Funktion.|

Wenn Sie möchten, können Sie das Dialogfeld über eine [in-Memory-Dialogfeld Vorlage](../mfc/using-a-dialog-template-in-memory.md) erstellen, die Sie erstellt haben, anstatt aus einer Dialogfeld Vorlagen Ressource. Dies ist jedoch ein erweitertes Thema.

## <a name="see-also"></a>Siehe auch

[Arbeiten mit Dialog Feldern in MFC](../mfc/life-cycle-of-a-dialog-box.md)
