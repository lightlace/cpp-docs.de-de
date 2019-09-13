---
title: Erstellen eigener Dialogfeldklassen
ms.date: 09/06/2019
helpviewer_keywords:
- dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- files [MFC], creating
- dialog classes [MFC], Add Class Wizard
- dialog classes [MFC], creating
ms.assetid: d5321741-da41-47a8-bb1c-6a0e8b28c4c1
ms.openlocfilehash: 424d18196063456245e2a4841b42e6e447bded17
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907328"
---
# <a name="creating-your-dialog-class"></a>Erstellen eigener Dialogfeldklassen

Erstellen Sie für jedes Dialogfeld in Ihrem Programm eine neue Dialogfeld Klasse, um mit der Dialogfeld Ressource zu arbeiten.

Durch das [Hinzufügen einer Klasse](../ide/adding-a-class-visual-cpp.md) wird erläutert, wie eine neue Dialogfeld Klasse erstellt wird. Wenn Sie eine Dialogfeld Klasse mit dem [Klassen-Assistenten](reference/mfc-class-wizard.md)erstellen, werden die folgenden Elemente in die von Ihnen angegebenen h-und CPP-Dateien geschrieben:

In der. h-Datei:

- Eine Klassen Deklaration für die Dialogfeld Klasse. Die-Klasse wird von [CDialog](../mfc/reference/cdialog-class.md)abgeleitet.

In der CPP-Datei:

- Eine Meldungs Zuordnung für die-Klasse.

- Ein Standardkonstruktor für das Dialogfeld.

- Eine außer Kraft setzung der [DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange) -Member-Funktion. Bearbeiten Sie diese Funktion. Sie wird für Dialog Datenaustausch und Validierungs Funktionen verwendet, die weiter unten unter [Dialog Datenaustausch und Validierung](../mfc/dialog-data-exchange-and-validation.md)beschrieben werden.

## <a name="see-also"></a>Siehe auch

[Erstellen einer Dialogfeldklasse mit Code-Assistenten](../mfc/creating-a-dialog-class-with-code-wizards.md)<br/>
[Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)
