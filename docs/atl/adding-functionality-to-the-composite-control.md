---
title: Hinzufügen von Funktionen zum zusammengesetzten Steuerelement | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- event handlers [C++], ActiveX controls
- composite controls, handling events
- ActiveX controls [C++], events
ms.assetid: 98f85681-9564-480d-af38-03f9733fe58b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 59ee8047e17efdebbae6ee58ec243057a477caff
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43751132"
---
# <a name="adding-functionality-to-the-composite-control"></a>Hinzufügen von Funktionen zum zusammengesetzten Steuerelement

Nachdem Sie alle erforderlichen Steuerelemente in das zusammengesetzte Steuerelement eingefügt haben, umfasst der nächste Schritt neue Funktionalität hinzufügen. Diese neue Funktionalität liegt in der Regel in zwei Kategorien unterteilt:

- Unterstützung zusätzlicher Schnittstellen, und das Verhalten des zusammengesetzten Steuerelements durch zusätzliche spezielle Features anpassen.

- Behandeln von Ereignissen der enthaltenen ActiveX-Steuerelement (oder Steuerelemente).

Für den Zweck und Umfang dieses Artikels im Mittelpunkt der übrige Teil dieses Abschnitts ausschließlich Behandeln von Ereignissen ActiveX-Steuerelemente.

> [!NOTE]
>  Wenn Sie Nachrichten von Windows-Steuerelemente behandeln müssen, finden Sie unter [Implementieren eines Fensters](../atl/implementing-a-window.md) für Weitere Informationen zu Meldungsbehandlung in ATL

Klicken Sie nach dem Einfügen eines ActiveX-Steuerelements in der Dialogfeldressource an, klicken Sie auf das Steuerelement, und klicken Sie auf **Ereignishandler hinzufügen**. Wählen Sie das Ereignis zu behandeln, und klicken Sie auf **hinzufügen und Bearbeiten von**. Der Code des ereignishandlers wird .h-Datei des Steuerelements hinzugefügt werden.

Verbindungspunkte für ActiveX-Steuerelemente für das zusammengesetzte Steuerelement werden automatisch verbunden und über Aufrufe von getrennt [:: AdviseSinkMap](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap).

## <a name="see-also"></a>Siehe auch

[Grundlagen von zusammengesetzten Steuerelementen](../atl/atl-composite-control-fundamentals.md)

