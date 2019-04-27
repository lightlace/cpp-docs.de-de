---
title: Dynamische Objekterstellung
ms.date: 11/04/2016
helpviewer_keywords:
- object creation [MFC], dynamically at run time
- CObject class [MFC], dynamic object creation
- objects [MFC], creating dynamically at run time
- dynamic object creation [MFC]
ms.assetid: 3e0f51cb-3e24-4231-817f-1c0ce9f2d5df
ms.openlocfilehash: 3478e5481c177e0ebca1e6b5c2cd07509371c5ef
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173354"
---
# <a name="dynamic-object-creation"></a>Dynamische Objekterstellung

In diesem Artikel wird erläutert, wie ein Objekt dynamisch zur Laufzeit erstellt wird. Die Prozedur verwendet die Laufzeit-Klasseninformationen, wie im folgenden Artikel beschrieben [zugreifen auf Laufzeit-Klasseninformationen](../mfc/accessing-run-time-class-information.md).

#### <a name="to-dynamically-create-an-object-given-its-run-time-class"></a>Um ein Objekt, das die Laufzeit-Klasse dynamisch zu erstellen.

1. Verwenden Sie den folgenden Code, erstellen Sie ein Objekt dynamisch mithilfe der `CreateObject` Funktion der `CRuntimeClass`. Beachten Sie, dass bei einem Fehler `CreateObject` gibt **NULL** statt eine Ausnahme auszulösen:

   [!code-cpp[NVC_MFCCObjectSample#6](../mfc/codesnippet/cpp/dynamic-object-creation_1.cpp)]

## <a name="see-also"></a>Siehe auch

[Verwenden von CObject](../mfc/using-cobject.md)
