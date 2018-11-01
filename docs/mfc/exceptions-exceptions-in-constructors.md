---
title: 'Ausnahmen: Ausnahmen in Konstruktoren | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- constructors [MFC], exceptions
- throwing exceptions [MFC], in constructors
- exceptions [MFC], in constructors
ms.assetid: a78eae5a-5821-4b27-9478-1436320ed1e1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3cab21255698c19046cfca185a0d8d7e7c530112
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46421933"
---
# <a name="exceptions-exceptions-in-constructors"></a>Ausnahmen: Ausnahmen in Konstruktoren

Beim Auslösen von Ausnahmen in einem Konstruktor, beliebige Objekte und speicherreservierungen von Ihnen vorgenommenen vor dem Auslösen der Ausnahme, wie unter Bereinigen [Ausnahmen: Auslösen von Ausnahmen aus Ihrer eigenen Funktionen](../mfc/exceptions-throwing-exceptions-from-your-own-functions.md).

Beim Auslösen von Ausnahmen in einem Konstruktor, wurde der Speicher für das Objekt selbst bereits mit der Zeit zugeordnet, die der Konstruktor aufgerufen wird. Daher wird der Compiler automatisch freigeben des Speicherplatzes durch das Objekt belegt wird, nachdem die Ausnahme ausgelöst wird.

Weitere Informationen finden Sie unter [Ausnahmen: Freigeben von Objekten in Ausnahmen](../mfc/exceptions-freeing-objects-in-exceptions.md).

## <a name="see-also"></a>Siehe auch

[Ausnahmebehandlung](../mfc/exception-handling-in-mfc.md)

