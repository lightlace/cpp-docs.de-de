---
title: UI-Unterstützungsklassen (ATL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.atl.ui
dev_langs:
- C++
helpviewer_keywords:
- user interfaces, support classes
- user interfaces, ATL classes
ms.assetid: 313dfc95-308a-4118-b919-5a3c3673b865
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1aa28c172b4eb22366d2af55d040cb52c9e84a31
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43755234"
---
# <a name="ui-support-classes"></a>UI-Unterstützungsklassen

Die folgenden Klassen bieten allgemeine Benutzeroberflächenautomatisierungs-Unterstützung:

- [IDocHostUIHandlerDispatch](../atl/reference/idochostuihandlerdispatch-interface.md) eine Schnittstelle für die Microsoft-HTML-Analyse- und -Rendering-Engine.

- [IOleObjectImpl](../atl/reference/ioleobjectimpl-class.md) Hauptmethoden, über die ein Container kommuniziert, mit einem Steuerelement enthält. Verwaltet die Aktivierung und Deaktivierung des direktes Steuerelemente.

- [IOleInPlaceObjectWindowlessImpl](../atl/reference/ioleinplaceobjectwindowlessimpl-class.md) verwaltet die Reaktivierung des direktes Steuerelemente. Ermöglicht ein fensterloses Steuerelement zum Empfangen von Nachrichten als auch zur Teilnahme an Drag & Drop-Vorgänge.

- [IOleInPlaceActiveObjectImpl](../atl/reference/ioleinplaceactiveobjectimpl-class.md) unterstützt die Kommunikation zwischen einem in-Place-Steuerelement und seinem Container.

- [IViewObjectExImpl](../atl/reference/iviewobjecteximpl-class.md) ermöglicht es einem Steuerelement, selbst nicht direkt anzeigen und den Container der Änderungen in die Anzeige zu benachrichtigen. Bietet Unterstützung für flimmerfreie zeichnen, viereckig noch transparent Steuerelemente und Treffertests.

## <a name="related-articles"></a>Verwandte Artikel

[ATL-Lernprogramm](../atl/active-template-library-atl-tutorial.md)

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../atl/atl-class-overview.md)

