---
title: "Hinzufügen von Steuerelementen zu einem Eigenschaftenblatt | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- controls [MFC], adding to property sheets
- property sheets, adding controls
ms.assetid: 24ad4c0b-c1db-4850-b9f0-34aae8d74571
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2acbbed1a253a502aea8b19af6fd16ddb343e3ec
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="adding-controls-to-a-property-sheet"></a>Hinzufügen von Steuerelementen zu einem Eigenschaftenblatt
Standardmäßig weist ein Eigenschaftenblatt Fensterbereich, für die Eigenschaftenseiten der Registerkartenindex und die Schaltflächen "OK", "Abbrechen", und "übernehmen. (Ein nicht modalen Eigenschaftenblatts verfügt nicht über die "OK". "Abbrechen", und wenden Sie die Schaltflächen.) Sie können andere Steuerelemente auf dem Eigenschaftenblatt hinzufügen. Beispielsweise können Sie ein Vorschaufenster hinzufügen, um rechts neben den Bereich der Eigenschaft, um dem Benutzer anzuzeigen, was die aktuellen Einstellungen aussehen würde, wenn auf ein externes Objekt angewendet.  
  
 Sie können Steuerelemente hinzufügen, auf dem Eigenschaftenblatt-Dialogfeld in der `OnCreate` Handler. Das Hinzufügen weiterer Steuerelemente in der Regel erfordert das Erweitern der Größe des dem Eigenschaftenblatt-Dialogfeld. Nach dem Aufruf der Basisklasse **CPropertySheet:: OnCreate**, rufen Sie [GetWindowRect](../mfc/reference/cwnd-class.md#getwindowrect) erweitern Sie des Rechtecks, um die Breite und Höhe des Fensters für das aktuell zugeordneten Eigenschaft abzurufen, Dimensionen und Aufruf [MoveWindow](../mfc/reference/cwnd-class.md#movewindow) so ändern Sie die Größe des Fensters für die Eigenschaft.  
  
## <a name="see-also"></a>Siehe auch  
 [Eigenschaftenblätter](../mfc/property-sheets-mfc.md)   
 [CPropertyPage-Klasse](../mfc/reference/cpropertypage-class.md)   
 [CPropertySheet-Klasse](../mfc/reference/cpropertysheet-class.md)
