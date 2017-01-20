---
title: "Message Maps (ATL)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, Meldungshandler"
  - "message maps, ATL"
ms.assetid: 9e100400-65c7-4a85-8857-4e6cb6dd7340
caps.latest.revision: 10
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Message Maps (ATL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Meldungszuordnung ordnet eine Handlerfunktion mit einer bestimmten Meldung, einen Befehl oder einer Benachrichtigung zu.  Mit [Meldungszuordnungsmakros](../atl/reference/message-map-macros-atl.md) ATL verwenden, können Sie eine Meldungszuordnung für ein Fenster angeben.  Die Fensterprozeduren in `CWindowImpl`, in `CDialogImpl` und in `CContainedWindowT` verweisen die Meldungen eines Fensters auf seine Meldungszuordnung.  
  
 [Meldungshandlerfunktionen](../atl/message-handler-functions.md) akzeptieren ein zusätzliches Argument vom Typ `BOOL&`.  Dieses Argument gibt an, ob eine Nachricht verarbeitet wurde, und wird zu `TRUE` standardmäßig festgelegt.  Eine Handlerfunktion kann das Argument auf `FALSE` dann festlegen, um anzugeben, dass eine Nachricht nicht bearbeitet hat.  In diesem Fall wird ATL fort, um nach einer Handlerfunktion weiter in der Meldungszuordnung zu suchen.  Mithilfe dieses Argument zu `FALSE` festlegen, können Sie Aktionen als Reaktion auf eine Nachricht zuerst ausführen und eine Standardverarbeitung oder eine andere Handlerfunktion zum Ende dann ermöglichen die Meldung behandelt.  
  
## Verkettete Meldungszuordnungen  
 ATL können Sie in auch den Kettenmeldungszuordnungen, das die Meldungsbehandlung auf eine Meldungszuordnung verweist, die in einer anderen Klasse definiert ist.  Beispielsweise können Sie Standardnachrichtbehandlung in einer separaten Klasse implementieren, um einheitliches Verhalten für alle Fenster bereitzustellen verkettend zu dieser Klasse.  Sie können auf eine Basisklasse oder einen Datenmember der Klasse verketten.  
  
 ATL unterstützt auch dynamische Verketten, die Sie der Kette zur Meldungszuordnung eines anderen Objekts zur Laufzeit ermöglicht.  Um dynamische Verketten zu implementieren, müssen Sie die Klasse von [CDynamicChain](../atl/reference/cdynamicchain-class.md) berechnen.  Deklarieren Sie dann das [CHAIN\_MSG\_MAP\_DYNAMIC](../Topic/CHAIN_MSG_MAP_DYNAMIC.md)\-Makro in der Meldungszuordnung.  `CHAIN_MSG_MAP_DYNAMIC` erfordert eine eindeutige Zahl, die das Objekt und die Meldungszuordnung identifiziert, mit denen Sie verketten.  Sie müssen diesen eindeutigen Wert durch einen Aufruf `CDynamicChain::SetChainEntry` definieren.  
  
 Sie können eine beliebige Klasse verketten, die eine Meldungszuordnung deklariert, vorausgesetzt die Klasse von [CMessageMap](../atl/reference/cmessagemap-class.md) abgeleitet.  `CMessageMap` können Objekte, um seine Meldungszuordnungen anderen Objekten verfügbar zu machen.  Beachten Sie, dass `CWindowImpl` bereits von `CMessageMap` abgeleitet.  
  
## Alternative Meldungszuordnungen  
 Schließlich ATL\-Unterstützungs\-alternativeMeldungszuordnungen deklariert, mit dem [ALT\_MSG\_MAP](../Topic/ALT_MSG_MAP.md)\-Makro.  Jede alternative Meldungszuordnung wird durch eine eindeutige Zahl identifiziert, die Sie zu `ALT_MSG_MAP` übergeben.  Verwenden von alternativen Meldungszuordnungen können Sie die Meldungen aus mehreren Fenstern in einer Zuordnung bearbeiten.  Beachten Sie das standardmäßig, `CWindowImpl` verwendet keine alternative Meldungszuordnungen.  Um diese Unterstützung hinzuzufügen, überschreiben Sie die `WindowProc`\-Methode im `CWindowImpl` von abgeleitete Klasse und rufen Sie `ProcessWindowMessage` mit dem Meldungszuordnungsbezeichner auf.  
  
## Siehe auch  
 [Implementing a Window](../atl/implementing-a-window.md)