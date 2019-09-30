---
title: Erstellen von modalen Dialogfeldern
ms.date: 11/04/2016
helpviewer_keywords:
- modal dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], modal
ms.assetid: 26c7a68c-79f6-4862-a5a8-6024984644d2
ms.openlocfilehash: ed0fe3b7ef8aeddea01f573bfe8e1c01a6b5b443
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685670"
---
# <a name="creating-modal-dialog-boxes"></a>Erstellen von modalen Dialogfeldern

Um ein modales Dialogfeld zu erstellen, rufen Sie einen der beiden öffentlichen Konstruktoren auf, die in [CDialog](../mfc/reference/cdialog-class.md)deklariert wurden. Rufen Sie als nächstes die [DoModal](../mfc/reference/cdialog-class.md#domodal) -Member-Funktion des Dialog Felds auf, um das Dialogfeld anzuzeigen, und verwalten Sie die Interaktion damit, bis der Benutzer OK oder Abbrechen auswählt. Durch diese Verwaltung von `DoModal` wird das Dialogfeld modal. Für modale Dialogfelder lädt `DoModal` die Dialogfeld Ressource.

## <a name="see-also"></a>Siehe auch

[Arbeiten mit Dialog Feldern in MFC](../mfc/life-cycle-of-a-dialog-box.md)
