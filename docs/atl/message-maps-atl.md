---
title: Meldungszuordnungen (ATL)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- message maps, ATL
- ATL, message handlers
ms.assetid: 9e100400-65c7-4a85-8857-4e6cb6dd7340
ms.openlocfilehash: 1b8b3fcb2f10f975ebdf68a285c7d5e364b9e1b4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62250131"
---
# <a name="message-maps-atl"></a>Meldungszuordnungen (ATL)

Eine meldungszuordnung ordnet eine bestimmte Nachricht, Befehls- oder Benachrichtigung eine Handlerfunktion zu. Mithilfe von ATL [Nachricht Zuordnungsmakros](../atl/reference/message-map-macros-atl.md), können Sie angeben, eine meldungszuordnung für ein Fenster. Fenster in den Verfahren in `CWindowImpl`, `CDialogImpl`, und `CContainedWindowT` eines Fensters-Nachrichten an seine meldungszuordnung, weiterzuleiten.

Die [Nachricht Handlerfunktionen](../atl/message-handler-functions.md) akzeptiert ein zusätzliches Argument vom Typ `BOOL&`. Dieses Argument gibt an, ob eine Nachricht verarbeitet wurde, und es ist standardmäßig auf "true" festgelegt. Eine Handlerfunktion kann dann das Argument festlegen, auf "false", um anzugeben, dass sie eine Nachricht nicht verarbeitet wurde. In diesem Fall weiterhin ATL für die Handlerfunktion einen weiter in die nachrichtenzuordnung suchen. Wenn dieses Argument auf "false" festlegen, können Sie zuerst führen Sie eine Aktion als Reaktion auf eine Nachricht und lassen Sie die standardmäßige Verarbeitung oder eine andere Handler-Funktion, um den Vorgang abzuschließen, zur Behandlung der Nachricht.

## <a name="chained-message-maps"></a>Verkettete Meldungszuordnungen

ATL ermöglicht Ihnen außerdem den meldungszuordnungen Kette, die die Nachricht, die Ausnahmebehandlung einer meldungszuordnung, die in einer anderen Klasse definiert angewiesen. Beispielsweise können Sie allgemeine Behandlung von Nachrichten in einer separaten Klasse uniform Verhalten für alle Fenster, die Verkettung zu dieser Klasse zu implementieren. Sie können auf eine Basisklasse oder ein Datenmember einer Klasse verketten.

ATL unterstützt auch dynamische verketten, wodurch Sie zu verketten, um ein anderes Objekt in die nachrichtenzuordnung zur Laufzeit. Um dynamische verketten zu implementieren, müssen Sie ableiten der Klasse aus [CDynamicChain](../atl/reference/cdynamicchain-class.md). Anschließend deklariert der [CHAIN_MSG_MAP_DYNAMIC](reference/message-map-macros-atl.md#chain_msg_map_dynamic) Makro in der meldungszuordnung. CHAIN_MSG_MAP_DYNAMIC erfordert eine eindeutige Zahl, die das Objekt und die meldungszuordnung, die auf die Sie verketten werden bestimmt. Definieren Sie mit diesem eindeutigen Wert durch einen Aufruf von `CDynamicChain::SetChainEntry`.

Sie können auf jede Klasse, die eine meldungszuordnung, deklariert verketten, sofern die Klasse abgeleitet [CMessageMap](../atl/reference/cmessagemap-class.md). `CMessageMap` ermöglicht einem Objekt, dessen meldungszuordnungen auf andere Objekte verfügbar zu machen. Beachten Sie, dass `CWindowImpl` abgeleitet `CMessageMap`.

## <a name="alternate-message-maps"></a>Alternative Meldungszuordnungen

Schließlich ATL unterstützt alternativen meldungszuordnungen, mit dem deklariert die [ALT_MSG_MAP](reference/message-map-macros-atl.md#alt_msg_map) Makro. Jede alternative meldungszuordnung wird durch eine eindeutige Nummer, identifiziert, die Sie an ALT_MSG_MAP übergeben. Mithilfe von alternativen Nachricht Karten, Sie können mehrere Fenster in einer Zuordnung die Nachrichten verarbeiten. Beachten Sie, dass in der Standardeinstellung `CWindowImpl` verwendet keine alternativen meldungszuordnungen. Um diese Unterstützung hinzuzufügen, überschreiben die `WindowProc` -Methode in der Ihre `CWindowImpl`-abgeleitete Klasse, und rufen `ProcessWindowMessage` mit der Nachrichten-ID zuordnen.

## <a name="see-also"></a>Siehe auch

[Implementieren eines Fensters](../atl/implementing-a-window.md)
