---
title: "Hinzufügen einer ATL-Meldungshandlers | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- message handlers [C++]
- ATL, windows
- message handling [C++], ATL message handler
- windows [C++], ATL
- ATL, message handlers
ms.assetid: cdea38a1-0d9b-4f8d-bbd5-b4f063fb3eeb
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4358dc54589971c559bec48adf77252d4f4cda28
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="adding-an-atl-message-handler"></a>Hinzufügen einer ATL-Meldungshandlers
Um ein Steuerelement einen Meldungshandler (eine Memberfunktion, die Windows-Meldungen behandelt) hinzuzufügen, müssen Sie zuerst wählen Sie das Steuerelement in der Klassenansicht aus. Öffnen Sie dann die **Eigenschaften** wählen die **Nachrichten** Symbol, und klicken Sie auf die Dropdownliste zu steuern, in das Feld gegenüber der Nachricht erforderlich. Dadurch wird eine Deklaration für die Message-Handler in der Headerdatei des Steuerelements und eine Skeleton-Implementierung des Handlers in cpp-Datei für das Steuerelement hinzugefügt. Außerdem werden die meldungszuordnung hinzufügen und fügen Sie einen Eintrag für den Handler.  
  
 Hinzufügen eines meldungshandlers in ATL ist vergleichbar mit dem Hinzufügen eines meldungshandlers eine MFC-Klasse. Finden Sie unter [Hinzufügen einer MFC-Meldungshandlers](../mfc/reference/adding-an-mfc-message-handler.md) für Weitere Informationen.  
  
 Die folgenden Bedingungen gelten nur für eine ATL-Meldungshandler hinzufügen:  
  
-   Die Message-Handler führen Sie dieselbe Namenskonvention wie MFC.  
  
-   Die neue Nachricht Zuordnungseinträge werden in die Hauptnachricht Zuordnung hinzugefügt. Der Assistent erkennt keine alternative nachrichtenzuordnungen und verketten.  
  
## <a name="see-also"></a>Siehe auch  
 [Implementieren eines Fensters](../atl/implementing-a-window.md)

