---
title: Auswählen eines Grafikobjekts für einen Gerätekontext | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- graphic objects [MFC], selecting into device context
- SelectObject method [MFC]
- GDI objects [MFC], device contexts
- lifetime, graphic objects [MFC]
- device contexts, selecting graphic objects into
- device contexts, graphic objects [MFC]
ms.assetid: cf54a330-63ef-421f-83eb-90ec7bd82eef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 406c4e7cd87b350f9317022dcf1821fa92ddf4af
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46427666"
---
# <a name="selecting-a-graphic-object-into-a-device-context"></a>Auswählen eines Grafikobjekts für einen Gerätekontext

Dieses Thema gilt für die grafische Objekte im Gerätekontext eines Fensters mit. Nachdem Sie [erstellen Sie ein Zeichnungsobjekt](../mfc/one-stage-and-two-stage-construction-of-objects.md), müssen Sie diesen auswählen, für den Gerätekontext anstelle der Default-Objekt, das dort gespeichert:

[!code-cpp[NVC_MFCDocViewSDI#7](../mfc/codesnippet/cpp/selecting-a-graphic-object-into-a-device-context_1.cpp)]

## <a name="lifetime-of-graphic-objects"></a>Lebensdauer von Grafikobjekten

Das Grafikobjekt zurückgegebenes [SelectObject](../mfc/reference/cdc-class.md#selectobject) ist "vorübergehend". Er wird, also gelöscht werden, indem die [OnIdle](../mfc/reference/cwinapp-class.md#onidle) Memberfunktion der Klasse `CWinApp` Zeit der nächsten Ausführung des Programms im Leerlauf befindet ruft. Solange Sie das zurückgegebene Objekt verwenden `SelectObject` in einer einzelnen Funktion ohne das Zurückgeben der Steuerung an die primäre Meldungsschleife, müssen Sie kein Problem.

### <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Grafikobjekte](../mfc/graphic-objects.md)

- [Ein- und zweistufige Konstruktion von Grafikobjekten](../mfc/one-stage-and-two-stage-construction-of-objects.md)

- [Gerätekontexte](../mfc/device-contexts.md)

- [Zeichnen in einer Ansicht](../mfc/drawing-in-a-view.md)

## <a name="see-also"></a>Siehe auch

[Grafikobjekte](../mfc/graphic-objects.md)

