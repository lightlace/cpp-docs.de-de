---
title: Struktur von Benachrichtigungsmeldungen des Registersteuerelements | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- notifications [MFC], tree controls
- messages [MFC], notification
- CTreeCtrl class [MFC], notifications
- notifications [MFC], CTreeCtrl
- tree controls [MFC], notification messages
ms.assetid: ac7013b4-91dd-4668-bd75-439ca0680ef9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 07911dec25bf9d6b80f025e2f3738e3d98ffd2cb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46390746"
---
# <a name="tree-control-notification-messages"></a>Benachrichtigungsmeldungen von Struktursteuerelementen

Ein Strukturansicht-Steuerelement ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) sendet die folgenden benachrichtigungsmeldungen als WM_NOTIFY-Meldungen:

|Benachrichtigungsmeldung|Beschreibung|
|--------------------------|-----------------|
|TVN_BEGINDRAG|Signalisiert den Start eines Drag & Drop-Vorgangs|
|TVN_BEGINLABELEDIT|Signalisiert den Start des direktes Bezeichnung bearbeiten|
|TVN_BEGINRDRAG|Signalisiert den Start eines Drag & Drop-Vorgangs, mit der rechten Maustaste|
|TVN_DELETEITEM|Signalisiert das Löschen eines bestimmten Elements|
|TVN_ENDLABELEDIT|Signalisiert das Ende der Bezeichnung bearbeiten|
|TVN_GETDISPINFO|Fordert Informationen, dass das Strukturansicht-Steuerelement erforderlich, zum Anzeigen eines Elements ist|
|TVN_ITEMEXPANDED|Signalisiert, dass ein übergeordnetes Element der Liste der untergeordneten Elemente erweitert oder reduziert wurde.|
|TVN_ITEMEXPANDING|Signalisiert, die dass ein übergeordnetes Element der Liste der untergeordneten Elemente ist dabei, erweitert oder reduziert werden|
|TVN_KEYDOWN|Signalisiert ein Tastaturereignis|
|EINE TVN_SELCHANGED|Signale, die die Auswahl von einem Element zum anderen geändert hat|
|TVN_SELCHANGING|Signalisiert, die dass die Auswahl ist von einem Element in eine andere geändert wird|
|TVN_SETDISPINFO|Benachrichtigung zum Aktualisieren der Informationen für ein Element verwaltet|

## <a name="see-also"></a>Siehe auch

[Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

