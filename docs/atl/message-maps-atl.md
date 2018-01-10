---
title: Meldungszuordnungen (ATL) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- message maps, ATL
- ATL, message handlers
ms.assetid: 9e100400-65c7-4a85-8857-4e6cb6dd7340
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1e708fea75c594c7bb9504515c80222ad901c335
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="message-maps-atl"></a>Meldungszuordnungen (ATL)
Eine meldungszuordnung ordnet eine bestimmte Meldung, einen Befehl oder Benachrichtigung eine Handlerfunktion. Mithilfe des ATL- [Nachricht Zuordnungsmakros](../atl/reference/message-map-macros-atl.md), Sie können eine meldungszuordnung für ein Fenster angeben. Die Fensterprozeduren in `CWindowImpl`, `CDialogImpl`, und `CContainedWindowT` ein Fenster seine meldungszuordnung, Nachrichten weiterleiten.  
  
 Die [Handler Nachrichtenfunktionen](../atl/message-handler-functions.md) akzeptiert ein zusätzliches Argument vom Typ `BOOL&`. Dieses Argument gibt an, ob eine Nachricht verarbeitet wurde, und ist, dass festgelegt ist `TRUE` standardmäßig. Eine Handlerfunktion kann dann legen Sie das Argument zu `FALSE` um anzugeben, dass sie eine Nachricht nicht verarbeitet wurde. In diesem Fall weiterhin ATL für die Handlerfunktion einen weiter in der meldungszuordnung gesucht werden soll. Durch Festlegen dieses Argument auf `FALSE`, führen Sie zuerst eine Aktion als Antwort auf eine Nachricht und lassen Sie die standardverarbeitung oder einen anderen Handler-Funktion zum Verarbeiten der Nachricht abgeschlossen werden können.  
  
## <a name="chained-message-maps"></a>Verkettete Meldungszuordnungen  
 ATL ermöglicht Ihnen auch, meldungszuordnungen Kette, die leitet die Meldungsbehandlung zu einer meldungszuordnung, die in einer anderen Klasse definiert. Beispielsweise können Sie allgemeine Meldungsbehandlung in einer separaten Klasse uniform Verhalten für alle Fenster, die für diese Klasse Verkettung bereitstellen implementieren. Sie können auf eine Basisklasse oder einem Datenmember einer Klasse verkettet.  
  
 ATL unterstützt auch dynamische verketten, womit Sie zu verketten, um ein anderes Objekt meldungszuordnung zur Laufzeit. Um dynamische verketten zu implementieren, leiten Sie eine Klasse von [CDynamicChain](../atl/reference/cdynamicchain-class.md). Anschließend deklariert der [CHAIN_MSG_MAP_DYNAMIC](reference/message-map-macros-atl.md#chain_msg_map_dynamic) Makro in Ihrer nachrichtenzuordnung. `CHAIN_MSG_MAP_DYNAMIC`erfordert eine eindeutige Zahl, die das Objekt und die meldungszuordnung, die Sie verketten werden, identifiziert. Sie müssen diesen eindeutigen Wert durch einen Aufruf von definieren `CDynamicChain::SetChainEntry`.  
  
 Sie können auf jede Klasse, die eine meldungszuordnung deklariert verketten, vorausgesetzt die Klasse abgeleitet [CMessageMap](../atl/reference/cmessagemap-class.md). `CMessageMap`ermöglicht es einem Objekt, dessen meldungszuordnungen zu anderen Objekten verfügbar zu machen. Beachten Sie, dass `CWindowImpl` bereits leitet sich von `CMessageMap`.  
  
## <a name="alternate-message-maps"></a>Alternative Meldungszuordnungen  
 Schließlich unterstützt ATL alternativen meldungszuordnungen deklariert, mit der [ALT_MSG_MAP](reference/message-map-macros-atl.md#alt_msg_map) Makro. Jede alternative meldungszuordnung wird durch eine eindeutige Nummer, die Sie übergeben identifiziert `ALT_MSG_MAP`. Unter Verwendung alternativer Meldung zugeordnet ist, können Sie die Nachrichten von mehreren Fenstern in eine Zuordnung behandeln. Beachten Sie, dass standardmäßig `CWindowImpl` alternativen meldungszuordnungen nicht verwendet. Um diese Unterstützung hinzuzufügen, überschreiben die `WindowProc` Methode in Ihrer `CWindowImpl`-abgeleitete Klasse, und rufen `ProcessWindowMessage` mit der Nachrichten-ID zuordnen.  
  
## <a name="see-also"></a>Siehe auch  
 [Implementieren eines Fensters](../atl/implementing-a-window.md)

