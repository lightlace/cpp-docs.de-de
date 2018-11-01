---
title: 'Ausnahmen: Ausnahmen in Konstruktoren'
ms.date: 11/04/2016
helpviewer_keywords:
- constructors [MFC], exceptions
- throwing exceptions [MFC], in constructors
- exceptions [MFC], in constructors
ms.assetid: a78eae5a-5821-4b27-9478-1436320ed1e1
ms.openlocfilehash: 23d1f6a9a3c76cc9c0c1d4aebd5c0b0ea45c3154
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50472267"
---
# <a name="exceptions-exceptions-in-constructors"></a>Ausnahmen: Ausnahmen in Konstruktoren

Beim Auslösen von Ausnahmen in einem Konstruktor, beliebige Objekte und speicherreservierungen von Ihnen vorgenommenen vor dem Auslösen der Ausnahme, wie unter Bereinigen [Ausnahmen: Auslösen von Ausnahmen aus Ihrer eigenen Funktionen](../mfc/exceptions-throwing-exceptions-from-your-own-functions.md).

Beim Auslösen von Ausnahmen in einem Konstruktor, wurde der Speicher für das Objekt selbst bereits mit der Zeit zugeordnet, die der Konstruktor aufgerufen wird. Daher wird der Compiler automatisch freigeben des Speicherplatzes durch das Objekt belegt wird, nachdem die Ausnahme ausgelöst wird.

Weitere Informationen finden Sie unter [Ausnahmen: Freigeben von Objekten in Ausnahmen](../mfc/exceptions-freeing-objects-in-exceptions.md).

## <a name="see-also"></a>Siehe auch

[Ausnahmebehandlung](../mfc/exception-handling-in-mfc.md)

