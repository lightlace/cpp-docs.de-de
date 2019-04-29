---
title: Auswählen eines Grafikobjekts für einen Gerätekontext
ms.date: 11/04/2016
helpviewer_keywords:
- graphic objects [MFC], selecting into device context
- SelectObject method [MFC]
- GDI objects [MFC], device contexts
- lifetime, graphic objects [MFC]
- device contexts, selecting graphic objects into
- device contexts, graphic objects [MFC]
ms.assetid: cf54a330-63ef-421f-83eb-90ec7bd82eef
ms.openlocfilehash: 7fb1507c1200da4cdf44627557ff6993e927d51e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62308526"
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
