---
title: Arbeiten mit dem Registersteuerelement | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CTabCtrl class [MFC], using
- tab controls [MFC], working with
- tab controls [MFC], using
ms.assetid: 819488e3-4944-44b7-9483-195edb8e0aed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 12de4065774c4813eeb10fab902551db14d10d3a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46420841"
---
# <a name="working-with-a-tab-control"></a>Arbeiten mit dem Registersteuerelement

Die einfachste Möglichkeit zum Verwenden eines Registerkarten-Steuerelements ([CTabCtrl](../mfc/reference/ctabctrl-class.md)) ist, indem sie Sie einer Dialogfeldvorlagen-Ressource hinzufügen, mit dem Dialog-Editor. Sie können auch ein Registerkarten-Steuerelement selbst. MFC-Aufrufe `InitCommonControls` für Sie. Die Hauptaufgaben der lauten wie folgt aus:

- [Erstellen des Registersteuerelements](../mfc/creating-the-tab-control.md)

- [Hinzufügen von Registerkarten zum Registerkarten-Steuerelement](../mfc/adding-tabs-to-a-tab-control.md)

- [Verarbeiten von benachrichtigungsmeldungen des Registersteuerelements](../mfc/processing-tab-control-notification-messages.md)

Wenn das Registerkarten-Steuerelementobjekt in einer übergeordneten Ansichts- oder Dialogfeldobjekt Klasse eingebettet ist, wird das Steuerelement zerstört, wenn das übergeordnete Element zerstört wird.

## <a name="see-also"></a>Siehe auch

[Verwenden von CTabCtrl](../mfc/using-ctabctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

