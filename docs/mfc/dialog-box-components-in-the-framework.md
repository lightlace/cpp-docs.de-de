---
title: Dialogfeld-Steuerelemente im Framework
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], creating
- dialog classes [MFC], dialog box components
- MFC dialog boxes [MFC], about MFC dialog boxes
- dialog templates [MFC], MFC framework
- MFC dialog boxes [MFC], dialog resource
ms.assetid: 592db160-0a8a-49be-ac72-ead278aca53f
ms.openlocfilehash: 15d01924be811a9c9ec8ea333870f444bf9aa61a
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685830"
---
# <a name="dialog-box-components-in-the-framework"></a>Dialogfeld-Steuerelemente im Framework

Im MFC-Framework verfügt ein Dialogfeld über zwei Komponenten:

- Eine Dialogfeld Vorlagen-Ressource, die die Steuerelemente des Dialog Felds und deren Platzierung angibt.

   Die Dialogfeld Ressource speichert eine Dialogfeld Vorlage, in der Windows das Dialogfenster erstellt und anzeigt. Die Vorlage gibt die Merkmale des Dialog Felds an, einschließlich der Größe, Position, Art und der Typen und Positionen der Steuerelemente des Dialog Felds. Normalerweise verwenden Sie eine Dialogfeld Vorlage, die als Ressource gespeichert wird, aber Sie können auch eine eigene Vorlage im Arbeitsspeicher erstellen.

- Eine aus [CDialog](../mfc/reference/cdialog-class.md)abgeleitete Dialogfeld Klasse, die eine programmgesteuerte Schnittstelle zum Verwalten des Dialog Felds bereitstellt.

   Ein Dialogfeld ist ein Fenster, das an ein Windows-Fenster angefügt wird, wenn es sichtbar ist. Wenn das Dialogfeld erstellt wird, wird die Ressource "Dialogfeld Vorlage" als Vorlage zum Erstellen von Steuerelementen für untergeordnete Fenster für das Dialogfeld verwendet.

## <a name="see-also"></a>Siehe auch

[Dialogfelder](../mfc/dialog-boxes.md)<br/>
[Arbeiten mit Dialog Feldern in MFC](../mfc/life-cycle-of-a-dialog-box.md)
