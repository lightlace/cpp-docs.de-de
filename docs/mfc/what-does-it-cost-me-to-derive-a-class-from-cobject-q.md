---
title: Welcher Overhead entsteht beim Ableiten einer Klasse von CObject?
ms.date: 11/04/2016
f1_keywords:
- CObject
helpviewer_keywords:
- CObject class [MFC], overhead of derived classes [MFC]
ms.assetid: 9b92c98b-b3dd-48a7-9d24-c3b8554edf90
ms.openlocfilehash: 521b6a32e3e5b34b4da9dab3117d55a728bd8e88
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50500449"
---
# <a name="what-does-it-cost-me-to-derive-a-class-from-cobject"></a>Welcher Overhead entsteht beim Ableiten einer Klasse von CObject?

Der Aufwand beim Ableiten einer Klasse [CObject](../mfc/reference/cobject-class.md) ist sehr einfach gehalten. Die abgeleitete Klasse erbt, nur vier virtuelle Funktionen und einem einzelnen [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) Objekt.

## <a name="see-also"></a>Siehe auch

[CObject-Klasse: Häufig gestellte Fragen](../mfc/cobject-class-frequently-asked-questions.md)
