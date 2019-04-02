---
title: 'ATL-Steuerelementen: Allgemeine Supportklassen'
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- controls [ATL]
- general support classes
ms.assetid: cf73f1d2-7542-48e3-b8c8-9d3abf29f85b
ms.openlocfilehash: 3f00348ab0c9f25bdd4f6b7a2b05cd4b82ea48e9
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58775269"
---
# <a name="controls-general-support-classes"></a>Steuerelemente: Allgemeine Supportklassen

Die folgenden Klassen bieten allgemeine Unterstützung für ATL-Steuerelementen an:

- [CComControl](../atl/reference/ccomcontrol-class.md) besteht aus Helper-Funktionen und Datenmember, die ATL-Steuerelementen von wesentlicher Bedeutung sind.

- [IOleControlImpl](../atl/reference/iolecontrolimpl-class.md) bietet Methoden, die für Steuerelemente erforderlich sind.

- [IOleObjectImpl](../atl/reference/ioleobjectimpl-class.md) Hauptmethoden, über die ein Container kommuniziert, mit einem Steuerelement enthält. Verwaltet die Aktivierung und Deaktivierung des direktes Steuerelemente.

- [IQuickActivateImpl](../atl/reference/iquickactivateimpl-class.md) kombiniert Initialisierung in einem einzigen Aufruf Verzögerungen zu vermeiden, beim Laden der Steuerelemente von Containern zu unterstützen.

- [IPointerInactiveImpl](../atl/reference/ipointerinactiveimpl-class.md) minimale Mausinteraktion für ein ansonsten Inaktives Steuerelement enthält.

## <a name="sample-program"></a>Beispielprogramm

[ATLFire](../overview/visual-cpp-samples.md)

## <a name="related-articles"></a>Verwandte Artikel

[ATL-Lernprogramm](../atl/active-template-library-atl-tutorial.md)

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../atl/atl-class-overview.md)
