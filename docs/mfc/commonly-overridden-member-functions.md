---
title: Überschreibbare Memberfunktionen
ms.date: 09/06/2019
helpviewer_keywords:
- CDialog class [MFC], members
- OnInitDialog function
- dialog classes [MFC], commonly overridden member functions
- OnCancel function
- overriding, dialog class members
- OnOK function
- MFC dialog boxes [MFC], overriding member functions
ms.assetid: 78eb566c-e361-4c86-8db5-c7e2791b249a
ms.openlocfilehash: 51a647bb50415af71d6d148d3139f906f503ee2a
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685821"
---
# <a name="commonly-overridden-member-functions"></a>Überschreibbare Memberfunktionen

In der folgenden Tabelle sind die wahrscheinlichsten Element Funktionen aufgelistet, die `CDialog`in der von abgeleiteten Klasse überschrieben werden müssen.

### <a name="commonly-overridden-member-functions-of-class-cdialog"></a>Häufig überschriebene Member-Funktionen der CDialog-Klasse

|Member-Funktion|Meldung, auf die reagiert wird|Zweck der außer Kraft Setzung|
|---------------------|----------------------------|-----------------------------|
|`OnInitDialog`|**WM_INITDIALOG**|Initialisieren Sie die Steuerelemente des Dialog Felds.|
|`OnOK`|**BN_CLICKED** für Schaltfläche **IDOK**|Reagiert, wenn der Benutzer auf die Schaltfläche "OK" klickt.|
|`OnCancel`|**BN_CLICKED** für Schaltfläche **IDCANCEL**|Reagiert, wenn der Benutzer auf die Schaltfläche Abbrechen klickt.|

`OnInitDialog`, `OnOK` und`OnCancel` sind virtuelle Funktionen. Um diese zu überschreiben, deklarieren Sie mithilfe des [MFC-Klassen-Assistenten](reference/mfc-class-wizard.md)eine über schreibende Funktion in der abgeleiteten Dialog Klasse.

`OnInitDialog`wird aufgerufen, kurz bevor das Dialogfeld angezeigt wird. Sie müssen den Standard `OnInitDialog` Handler von ihrer Überschreibungs – (in der Regel als erste Aktion im-Handler) aufzurufen. Standardmäßig `OnInitDialog` gibt **true** zurück, um anzugeben, dass der Fokus auf das erste Steuerelement im Dialogfeld festgelegt werden soll.

`OnOK`wird in der Regel für nicht modale, aber keine modale Dialogfelder überschrieben. Wenn Sie diesen Handler für ein modales Dialogfeld außer Kraft setzen, müssen Sie die Basisklassen Version von ihrer Überschreibungs – aufrufen, um `EndDialog` sicherzustellen, dass `EndDialog` – aufgerufen wird, oder selbst aufrufen.

`OnCancel`wird in der Regel für nicht modlose Dialogfelder überschrieben.

Weitere Informationen zu diesen Element Funktionen finden Sie unter Class [CDialog](../mfc/reference/cdialog-class.md) in der *MFC-Referenz* und in der Diskussion über das [Arbeiten mit Dialog Feldern in MFC](../mfc/life-cycle-of-a-dialog-box.md).

## <a name="see-also"></a>Siehe auch

[Dialogfelder](../mfc/dialog-boxes.md)<br/>
[Häufig hinzugefügte Memberfunktionen](../mfc/commonly-added-member-functions.md)
