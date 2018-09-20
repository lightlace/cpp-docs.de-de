---
title: Erstellen und Anzeigen von Dialogfeldern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- modal dialog boxes [MFC], creating
- opening dialog boxes
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], displaying
ms.assetid: 1c5219ee-8b46-44bc-9708-83705d4f248b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 437fb934e95ce527a77038d643e9cee86b6f1f2c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387743"
---
# <a name="creating-and-displaying-dialog-boxes"></a>Erstellen und Anzeigen von Dialogfeldern

Erstellen ein-Objekt eines Dialogfelds ist ein zweistufiger Prozess. Zunächst erstellen Sie das Dialogfeldobjekt, und erstellen Sie dann das Dialogfeld. Modale und nicht modale Dialogfelder unterscheiden sich leicht in der Vorgehensweise zum Erstellen und diese anzeigen. Die folgende Tabelle enthält wie modale und nicht modale Dialogfeld Felder normalerweise erstellt und angezeigt werden.

### <a name="dialog-creation"></a>Dialogfeld-Erstellung

|Dialogfeldtyp|Zum Erstellen|
|-----------------|----------------------|
|[Ohne Modus](../mfc/creating-modeless-dialog-boxes.md)|Erstellen Sie `CDialog`, rufen Sie anschließend `Create` Member-Funktion.|
|[Modale](../mfc/creating-modal-dialog-boxes.md)|Erstellen Sie `CDialog`, rufen Sie anschließend `DoModal` Member-Funktion.|

Sie können, wenn Sie möchten, erstellen das Dialogfeld aus einer [Dialogfeldvorlage im Speicher](../mfc/using-a-dialog-template-in-memory.md) , den Sie erstellt haben und nicht aus einer Dialogfeldvorlagen-Ressource. Dies ist jedoch ein Thema für fortgeschrittene.

## <a name="see-also"></a>Siehe auch

[Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)

