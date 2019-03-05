---
title: Welcher Overhead entsteht beim Ableiten einer Klasse von CObject?
ms.date: 11/04/2016
f1_keywords:
- CObject
helpviewer_keywords:
- CObject class [MFC], overhead of derived classes [MFC]
ms.assetid: 9b92c98b-b3dd-48a7-9d24-c3b8554edf90
ms.openlocfilehash: de760a2fd2908595314dc09cf5a317da3581e3bb
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57326386"
---
# <a name="what-does-it-cost-me-to-derive-a-class-from-cobject"></a>Welcher Overhead entsteht beim Ableiten einer Klasse von CObject?

Der Aufwand beim Ableiten einer Klasse [CObject](../mfc/reference/cobject-class.md) ist sehr einfach gehalten. Die abgeleitete Klasse erbt, nur vier virtuelle Funktionen und einem einzelnen [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) Objekt.

## <a name="see-also"></a>Siehe auch

[CObject-Klasse: Häufig gestellte Fragen](../mfc/cobject-class-frequently-asked-questions.md)
