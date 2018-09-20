---
title: Muss ich von CObject neue Klassen ableiten? | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CObject
dev_langs:
- C++
helpviewer_keywords:
- derived classes [MFC], from CObject
- CObject class [MFC], when to use
ms.assetid: 26021031-feaf-424c-80d1-9547c4409d6a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ec080e556b57afadbc3d958f4dba5ac6393108aa
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46408907"
---
# <a name="do-i-have-to-derive-new-classes-from-cobject"></a>Muss ich von CObject neue Klassen ableiten?

Nein, müssen Sie nicht.

Leiten Sie eine Klasse von [CObject](../mfc/reference/cobject-class.md) Wenn Sie die Funktionen sie bereitstellt benötigen, z. B. Serialisierung oder dynamische Creatability. Viele Datenklassen auf Dateien, serialisiert werden, daher es oft eine gute Idee ist, daraus ableiten müssen `CObject`. Für ein Beispiel für eine Klasse abgeleitet `CObject`, finden Sie unter den [Scribble-Beispiels](../visual-cpp-samples.md).

## <a name="see-also"></a>Siehe auch

[CObject-Klasse: Häufig gestellte Fragen](../mfc/cobject-class-frequently-asked-questions.md)
