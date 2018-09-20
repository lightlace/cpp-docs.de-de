---
title: CString-Ausnahmebereinigung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- CString objects, exceptions
- exception handling, cleanup code
ms.assetid: 28b9ce70-be63-4a0d-92a8-44bbfbc95e83
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 81349135fa822627cb40bdcd2570276d8040e50e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46385520"
---
# <a name="cstring-exception-cleanup"></a>CString-Ausnahmebereinigung

In früheren Versionen von MFC, war es wichtig, dass Sie bereinigen [CString](../atl-mfc-shared/reference/cstringt-class.md) Objekte nach der Verwendung. Mit MFC, Version 3.0 und höher ist eine explizite Bereinigung nicht mehr erforderlich.

In der C++-Ausnahmebehandlung Mechanismus, mit dem MFC jetzt verwendet, müssen Sie keinen Cleanup nach einer Ausnahme kümmern. Eine Beschreibung der wie C++ "entladen" im Stapel nach dem eine Ausnahme abgefangen wird, finden Sie unter [die Try-, catch- und throw-Anweisungen](../cpp/try-throw-and-catch-statements-cpp.md). Auch wenn Sie die MFC-Bibliothek verwenden **versuchen**/**CATCH** Makros anstelle der C++-Schlüsselwörter **versuchen Sie es** und **catch**, verwendet MFC C++ Ausnahmemechanismus, damit Sie immer noch müssen nicht explizit bereinigen.

## <a name="see-also"></a>Siehe auch

[Zeichenfolgen (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[Ausnahmebehandlung](../mfc/exception-handling-in-mfc.md)

