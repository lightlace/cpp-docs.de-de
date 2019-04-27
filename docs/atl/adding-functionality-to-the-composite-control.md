---
title: Hinzufügen von Funktionen zum zusammengesetzten Steuerelement
ms.date: 11/04/2016
helpviewer_keywords:
- event handlers [C++], ActiveX controls
- composite controls, handling events
- ActiveX controls [C++], events
ms.assetid: 98f85681-9564-480d-af38-03f9733fe58b
ms.openlocfilehash: 9ad7ef3d80579804ac614fbefac1a042a9cf2fba
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62252493"
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
