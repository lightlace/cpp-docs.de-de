---
title: Muss ich von CObject neue Klassen ableiten?
ms.date: 11/04/2016
f1_keywords:
- CObject
helpviewer_keywords:
- derived classes [MFC], from CObject
- CObject class [MFC], when to use
ms.assetid: 26021031-feaf-424c-80d1-9547c4409d6a
ms.openlocfilehash: c2361967dcfce5e46aeec65ade3d7056b362949d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50636604"
---
# <a name="do-i-have-to-derive-new-classes-from-cobject"></a>Muss ich von CObject neue Klassen ableiten?

Nein, müssen Sie nicht.

Leiten Sie eine Klasse von [CObject](../mfc/reference/cobject-class.md) Wenn Sie die Funktionen sie bereitstellt benötigen, z. B. Serialisierung oder dynamische Creatability. Viele Datenklassen auf Dateien, serialisiert werden, daher es oft eine gute Idee ist, daraus ableiten müssen `CObject`. Für ein Beispiel für eine Klasse abgeleitet `CObject`, finden Sie unter den [Scribble-Beispiels](../visual-cpp-samples.md).

## <a name="see-also"></a>Siehe auch

[CObject-Klasse: Häufig gestellte Fragen](../mfc/cobject-class-frequently-asked-questions.md)
