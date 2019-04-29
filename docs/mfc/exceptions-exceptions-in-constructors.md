---
title: 'Ausnahmen: Ausnahmen in Konstruktoren'
ms.date: 11/04/2016
helpviewer_keywords:
- constructors [MFC], exceptions
- throwing exceptions [MFC], in constructors
- exceptions [MFC], in constructors
ms.assetid: a78eae5a-5821-4b27-9478-1436320ed1e1
ms.openlocfilehash: 0b11f5be18879d5ad4b9e204bb02e18b4617c6b7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405871"
---
# <a name="exceptions-exceptions-in-constructors"></a>Ausnahmen: Ausnahmen in Konstruktoren

Beim Auslösen von Ausnahmen in einem Konstruktor, beliebige Objekte und speicherreservierungen von Ihnen vorgenommenen vor dem Auslösen der Ausnahme, wie unter Bereinigen [Ausnahmen: Auslösen von Ausnahmen in eigenen Funktionen](../mfc/exceptions-throwing-exceptions-from-your-own-functions.md).

Beim Auslösen von Ausnahmen in einem Konstruktor, wurde der Speicher für das Objekt selbst bereits mit der Zeit zugeordnet, die der Konstruktor aufgerufen wird. Daher wird der Compiler automatisch freigeben des Speicherplatzes durch das Objekt belegt wird, nachdem die Ausnahme ausgelöst wird.

Weitere Informationen finden Sie unter [Ausnahmen: Freigeben von Objekten in Ausnahmen](../mfc/exceptions-freeing-objects-in-exceptions.md).

## <a name="see-also"></a>Siehe auch

[Ausnahmebehandlung](../mfc/exception-handling-in-mfc.md)
