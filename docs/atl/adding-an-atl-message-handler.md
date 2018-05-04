---
title: Hinzufügen einer ATL-Meldungshandlers | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- message handlers [C++]
- ATL, windows
- message handling [C++], ATL message handler
- windows [C++], ATL
- ATL, message handlers
ms.assetid: cdea38a1-0d9b-4f8d-bbd5-b4f063fb3eeb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e79598b79ccbad13ad98c7fc1284808fe1b05cfc
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="adding-an-atl-message-handler"></a>Hinzufügen einer ATL-Meldungshandlers
Um ein Steuerelement einen Meldungshandler (eine Memberfunktion, die Windows-Meldungen behandelt) hinzuzufügen, müssen Sie zuerst wählen Sie das Steuerelement in der Klassenansicht aus. Öffnen Sie dann die **Eigenschaften** wählen die **Nachrichten** Symbol, und klicken Sie auf die Dropdownliste zu steuern, in das Feld gegenüber der Nachricht erforderlich. Dadurch wird eine Deklaration für die Message-Handler in der Headerdatei des Steuerelements und eine Skeleton-Implementierung des Handlers in cpp-Datei für das Steuerelement hinzugefügt. Außerdem werden die meldungszuordnung hinzufügen und fügen Sie einen Eintrag für den Handler.  
  
 Hinzufügen eines meldungshandlers in ATL ist vergleichbar mit dem Hinzufügen eines meldungshandlers eine MFC-Klasse. Finden Sie unter [Hinzufügen einer MFC-Meldungshandlers](../mfc/reference/adding-an-mfc-message-handler.md) für Weitere Informationen.  
  
 Die folgenden Bedingungen gelten nur für eine ATL-Meldungshandler hinzufügen:  
  
-   Die Message-Handler führen Sie dieselbe Namenskonvention wie MFC.  
  
-   Die neue Nachricht Zuordnungseinträge werden in die Hauptnachricht Zuordnung hinzugefügt. Der Assistent erkennt keine alternative nachrichtenzuordnungen und verketten.  
  
## <a name="see-also"></a>Siehe auch  
 [Implementieren eines Fensters](../atl/implementing-a-window.md)

