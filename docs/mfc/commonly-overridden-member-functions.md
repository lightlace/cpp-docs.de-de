---
title: Überschreibbare Memberfunktionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CDialog class [MFC], members
- OnInitDialog function
- dialog classes [MFC], commonly overridden member functions
- OnCancel function
- overriding, dialog class members
- OnOK function
- MFC dialog boxes [MFC], overriding member functions
ms.assetid: 78eb566c-e361-4c86-8db5-c7e2791b249a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: aabc88db4fcb2a484ca44feea8fcdf7727e23a16
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46431410"
---
# <a name="commonly-overridden-member-functions"></a>Überschreibbare Memberfunktionen

Die folgende Tabelle enthält die wahrscheinlichste Memberfunktionen überschreiben Sie in Ihrem `CDialog`-abgeleitete Klasse.

### <a name="commonly-overridden-member-functions-of-class-cdialog"></a>Überschreibbare Memberfunktionen der CDialog-Klasse

|Member-Funktion|Nachricht, die reagiert werden soll|Zweck der Außerkraftsetzung|
|---------------------|----------------------------|-----------------------------|
|`OnInitDialog`|**WM_INITDIALOG**|Initialisieren Sie das Dialogfeld-Steuerelemente.|
|`OnOK`|**BN_CLICKED** für Schaltfläche **IDOK**|Reagieren Sie, wenn der Benutzer die Schaltfläche "OK" klickt.|
|`OnCancel`|**BN_CLICKED** für Schaltfläche **IDCANCEL**|Reagieren Sie, wenn der Benutzer die Schaltfläche "Abbrechen" klickt.|

`OnInitDialog`, `OnOK`, und `OnCancel` sind virtuelle Funktionen. Um sie zu überschreiben, deklarieren Sie eine überschreibende-Funktion in der Klasse abgeleiteten Dialogfeld mit den [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window).

`OnInitDialog` wird aufgerufen, kurz bevor das Dialogfeld angezeigt wird. Müssen Sie die Standardeinstellung Aufrufen `OnInitDialog` -Handler aus der Außerkraftsetzung, in der Regel als die erste Aktion in den Handler. In der Standardeinstellung `OnInitDialog` gibt **"true"** um anzugeben, dass der Fokus auf das erste Steuerelement im Dialogfeld festgelegt werden soll.

`OnOK` wird für nicht modale, jedoch nicht modale Dialogfelder in der Regel überschrieben. Wenn Sie diese Handler für ein modales Dialogfeld überschreiben, rufen Sie die Basisklassenversion Ihre Überschreibung – um sicherzustellen, dass `EndDialog` aufgerufen wird, oder rufen Sie `EndDialog` selbst.

`OnCancel` wird in der Regel für nicht modale Dialogfelder überschrieben werden.

Weitere Informationen zu diesen Memberfunktionen finden Sie unter Klasse [CDialog](../mfc/reference/cdialog-class.md) in die *MFC-Referenz* und der Diskussion auf [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md).

## <a name="see-also"></a>Siehe auch

[Dialogfelder](../mfc/dialog-boxes.md)<br/>
[Häufig hinzugefügte Memberfunktionen](../mfc/commonly-added-member-functions.md)
