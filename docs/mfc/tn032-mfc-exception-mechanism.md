---
title: 'TN032: MFC-Ausnahmemechanismus'
ms.date: 11/04/2016
helpviewer_keywords:
- TN032
- MFC, exceptions
- CException class [MFC], using
ms.assetid: 0271f0aa-82cb-47a2-b7ea-e88126fc7e43
ms.openlocfilehash: 5b419fdcc4f20579b1a809dd8a5cf6a93f4fe835
ms.sourcegitcommit: 934cb53fa4cb59fea611bfeb9db110d8d6f7d165
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65611412"
---
# <a name="tn032-mfc-exception-mechanism"></a>TN032: MFC-Ausnahmemechanismus

Standard C++-Ausnahmemechanismus wurde von frühere Versionen von Visual C++ nicht unterstützt und MFC bereitgestellten Makros **TRY/CATCH/THROW** stattdessen verwendet wurden. C++-Ausnahmen werden von dieser Version von Visual C++ vollständig unterstützt. In diesem Hinweis behandelt einige der erweiterten Implementierungsdetails der vorherigen Makros auch automatisch basierenden Bereinigen von Objekten. Da C++-Ausnahmen stapelentladung standardmäßig unterstützt, ist diese technische Hinweis nicht mehr erforderlich.

Finden Sie unter [Ausnahmen: Mithilfe von MFC-Makros und C++-Ausnahmen](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md) für Weitere Informationen zu den Unterschieden zwischen den MFC-Makros und die neuen C++-Schlüsselwörter.

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)
