---
title: Hinzufügen eines ATL-Meldungshandlers | Microsoft-Dokumentation
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
ms.openlocfilehash: 712f1b725afd52057deca8f05047c91bfc4affce
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43753409"
---
# <a name="adding-an-atl-message-handler"></a>Hinzufügen eines ATL-Meldungshandlers

Um einen Meldungshandler (eine Memberfunktion, die Windows-Meldungen behandelt) ein Steuerelement hinzuzufügen, müssen Sie zuerst wählen Sie das Steuerelement in der Klassenansicht aus. Öffnen Sie dann die **Eigenschaften** wählen Sie im Fenster der **Nachrichten** Symbol, und klicken Sie auf die Dropdownliste zu steuern, in das Feld Gegenstück der Nachricht erforderlich sind. Dadurch wird eine Deklaration für die Message-Handler in der Headerdatei des Steuerelements und eine Skelett-Implementierung des Handlers in cpp-Datei des Steuerelements hinzugefügt. Außerdem wird die nachrichtenzuordnung hinzufügen und fügen Sie einen Eintrag für den Handler.

Hinzufügen eines meldungshandlers in ATL ist vergleichbar mit dem Hinzufügen eines meldungshandlers für eine MFC-Klasse. Finden Sie unter [Hinzufügen eines MFC-Meldungshandlers](../mfc/reference/adding-an-mfc-message-handler.md) für Weitere Informationen.

Die folgenden Bedingungen gelten nur für das Hinzufügen eines ATL-meldungshandlers:

- Der Meldungshandler führen Sie dieselben Namenskonventionen gelten wie MFC.

- Die neue Meldungszuordnungseinträge werden in der main-meldungszuordnung hinzugefügt. Der Assistent erkennt keine alternativen nachrichtenzuordnungen und verketten.

## <a name="see-also"></a>Siehe auch

[Implementieren eines Fensters](../atl/implementing-a-window.md)

