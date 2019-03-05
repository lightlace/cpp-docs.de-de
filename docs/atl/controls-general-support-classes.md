---
title: 'ATL-Steuerelementen: Allgemeine Supportklassen'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vc.atl.controls
helpviewer_keywords:
- controls [ATL]
- general support classes
ms.assetid: cf73f1d2-7542-48e3-b8c8-9d3abf29f85b
ms.openlocfilehash: bf5c1b9e2f4fb7414cc34d457bc0d8b1e27dcd91
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57262999"
---
# <a name="controls-general-support-classes"></a>Steuerelemente: Allgemeine Supportklassen

Die folgenden Klassen bieten allgemeine Unterstützung für ATL-Steuerelementen an:

- [CComControl](../atl/reference/ccomcontrol-class.md) besteht aus Helper-Funktionen und Datenmember, die ATL-Steuerelementen von wesentlicher Bedeutung sind.

- [IOleControlImpl](../atl/reference/iolecontrolimpl-class.md) bietet Methoden, die für Steuerelemente erforderlich sind.

- [IOleObjectImpl](../atl/reference/ioleobjectimpl-class.md) Hauptmethoden, über die ein Container kommuniziert, mit einem Steuerelement enthält. Verwaltet die Aktivierung und Deaktivierung des direktes Steuerelemente.

- [IQuickActivateImpl](../atl/reference/iquickactivateimpl-class.md) kombiniert Initialisierung in einem einzigen Aufruf Verzögerungen zu vermeiden, beim Laden der Steuerelemente von Containern zu unterstützen.

- [IPointerInactiveImpl](../atl/reference/ipointerinactiveimpl-class.md) minimale Mausinteraktion für ein ansonsten Inaktives Steuerelement enthält.

## <a name="sample-program"></a>Beispielprogramm

[ATLFire](../visual-cpp-samples.md)

## <a name="related-articles"></a>Verwandte Artikel

[ATL-Lernprogramm](../atl/active-template-library-atl-tutorial.md)

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../atl/atl-class-overview.md)
