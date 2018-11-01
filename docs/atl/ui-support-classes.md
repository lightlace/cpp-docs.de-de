---
title: UI-Unterstützungsklassen (ATL)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vc.atl.ui
helpviewer_keywords:
- user interfaces, support classes
- user interfaces, ATL classes
ms.assetid: 313dfc95-308a-4118-b919-5a3c3673b865
ms.openlocfilehash: 7306ddbbc3cf70850e0c7c66e48abf402017e5db
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50644222"
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

