---
title: Hinzufügen von Steuerelementen zu einem Eigenschaftenblatt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [MFC], adding to property sheets
- property sheets, adding controls
ms.assetid: 24ad4c0b-c1db-4850-b9f0-34aae8d74571
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0783571ed77d3d8dfaca69edf06330e62d8e98d0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46398498"
---
# <a name="adding-controls-to-a-property-sheet"></a>Hinzufügen von Steuerelementen zu einem Eigenschaftenblatt

Standardmäßig weist ein Eigenschaftenblatt Fensterbereich für die Eigenschaftenseiten, den Index der Aktivierreihenfolge und die Schaltflächen OK, "Abbrechen", und übernehmen. (Ein nicht modalen Eigenschaftenblatts verfügt nicht über OK, Abbrechen, und wenden Sie die Schaltflächen.) Sie können andere Steuerelemente auf dem Eigenschaftenblatt hinzufügen. Beispielsweise können Sie ein Fenster "Vorschau" hinzufügen, rechts vom Seitenbereich Eigenschaft, um dem Benutzer angezeigt, was die aktuellen Einstellungen aussehen würde, wenn auf ein externes Objekt angewendet.

Sie können Steuerelemente hinzufügen, auf dem Eigenschaftenblatt-Dialogfeld in der `OnCreate` Handler. In der Regel das Hinzufügen weiterer Steuerelemente ist erforderlich, erweitern die Größe der dem Eigenschaftenblatt-Dialogfeld. Nach dem Aufruf der Basisklasse **CPropertySheet:: OnCreate**, rufen Sie [GetWindowRect](../mfc/reference/cwnd-class.md#getwindowrect) rufen Sie die Breite und Höhe des Fensters für das aktuell zugeordneten Eigenschaft Erweitern des Rechtecks Dimensionen, und rufen [MoveWindow](../mfc/reference/cwnd-class.md#movewindow) so ändern Sie die Größe des Fensters für die Eigenschaft.

## <a name="see-also"></a>Siehe auch

[Eigenschaftenblätter](../mfc/property-sheets-mfc.md)<br/>
[CPropertyPage-Klasse](../mfc/reference/cpropertypage-class.md)<br/>
[CPropertySheet-Klasse](../mfc/reference/cpropertysheet-class.md)
