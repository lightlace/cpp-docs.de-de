---
title: CString-Ausnahmebereinigung
ms.date: 11/04/2016
helpviewer_keywords:
- CString objects, exceptions
- exception handling, cleanup code
ms.assetid: 28b9ce70-be63-4a0d-92a8-44bbfbc95e83
ms.openlocfilehash: f1950553e3bf3a43f029478e00b177f5cbfe121f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50492546"
---
# <a name="cstring-exception-cleanup"></a>CString-Ausnahmebereinigung

In früheren Versionen von MFC, war es wichtig, dass Sie bereinigen [CString](../atl-mfc-shared/reference/cstringt-class.md) Objekte nach der Verwendung. Mit MFC, Version 3.0 und höher ist eine explizite Bereinigung nicht mehr erforderlich.

In der C++-Ausnahmebehandlung Mechanismus, mit dem MFC jetzt verwendet, müssen Sie keinen Cleanup nach einer Ausnahme kümmern. Eine Beschreibung der wie C++ "entladen" im Stapel nach dem eine Ausnahme abgefangen wird, finden Sie unter [die Try-, catch- und throw-Anweisungen](../cpp/try-throw-and-catch-statements-cpp.md). Auch wenn Sie die MFC-Bibliothek verwenden **versuchen**/**CATCH** Makros anstelle der C++-Schlüsselwörter **versuchen Sie es** und **catch**, verwendet MFC C++ Ausnahmemechanismus, damit Sie immer noch müssen nicht explizit bereinigen.

## <a name="see-also"></a>Siehe auch

[Zeichenfolgen (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[Ausnahmebehandlung](../mfc/exception-handling-in-mfc.md)

