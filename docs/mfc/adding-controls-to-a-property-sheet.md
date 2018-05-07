---
title: Hinzufügen von Steuerelementen zu einem Eigenschaftenblatt | Microsoft Docs
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
ms.openlocfilehash: 8437fcdaa04ce7dd2b0a214e4bd3a63ca421d014
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="adding-controls-to-a-property-sheet"></a>Hinzufügen von Steuerelementen zu einem Eigenschaftenblatt
Standardmäßig weist ein Eigenschaftenblatt Fensterbereich, für die Eigenschaftenseiten der Registerkartenindex und die Schaltflächen "OK", "Abbrechen", und "übernehmen. (Ein nicht modalen Eigenschaftenblatts verfügt nicht über die "OK". "Abbrechen", und wenden Sie die Schaltflächen.) Sie können andere Steuerelemente auf dem Eigenschaftenblatt hinzufügen. Beispielsweise können Sie ein Vorschaufenster hinzufügen, um rechts neben den Bereich der Eigenschaft, um dem Benutzer anzuzeigen, was die aktuellen Einstellungen aussehen würde, wenn auf ein externes Objekt angewendet.  
  
 Sie können Steuerelemente hinzufügen, auf dem Eigenschaftenblatt-Dialogfeld in der `OnCreate` Handler. Das Hinzufügen weiterer Steuerelemente in der Regel erfordert das Erweitern der Größe des dem Eigenschaftenblatt-Dialogfeld. Nach dem Aufruf der Basisklasse **CPropertySheet:: OnCreate**, rufen Sie [GetWindowRect](../mfc/reference/cwnd-class.md#getwindowrect) erweitern Sie des Rechtecks, um die Breite und Höhe des Fensters für das aktuell zugeordneten Eigenschaft abzurufen, Dimensionen und Aufruf [MoveWindow](../mfc/reference/cwnd-class.md#movewindow) so ändern Sie die Größe des Fensters für die Eigenschaft.  
  
## <a name="see-also"></a>Siehe auch  
 [Eigenschaftenblätter](../mfc/property-sheets-mfc.md)   
 [CPropertyPage-Klasse](../mfc/reference/cpropertypage-class.md)   
 [CPropertySheet-Klasse](../mfc/reference/cpropertysheet-class.md)
