---
title: Eingabe-/ausgabealternativen
ms.date: 05/07/2019
helpviewer_keywords:
- I/O [C++], alternatives
ms.assetid: 9f8401c7-d90d-4285-8918-63573df74a80
ms.openlocfilehash: b46ff242fc263be5069eb691dd0ea9e8fb00b0f9
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455292"
---
# <a name="inputoutput-alternatives"></a>Eingabe-/Ausgabealternativen

Der Microsoft C++ -Compiler bietet mehrere Alternativen für die e/a-Programmierung:

- Direkte C-Laufzeitbibliothek, ungepufferte E/A.

- ANSI C-Laufzeitbibliotheksstream E/A.

- Direkte Konsole und Port-E/A.

- Microsoft Foundation Class-Bibliothek.

- Microsoft C++ Standardbibliothek.

Die iostream-Klassen sind für gepufferten, formatierten Text E/A nützlich. Sie sind auch für ungepufferte oder binäre E/A nützlich, wenn Sie eine C++-Programmierschnittstelle benötigen und nicht die Microsoft Foundation Class (MFC)-Bibliothek verwenden möchten. Die iostream-Klassen sind eine objektorientierte E/A-Alternative zu den C-Laufzeitfunktionen.

Sie können die iostream-Klassen mit dem Microsoft Windows-Betriebssystem verwenden. Zeichenfolgen- und Dateistreams arbeiten ohne Einschränkungen, aber die Streamobjekte im Zeichenmodus `cin`, `cout`, `cerr`, und `clog` sind inkonsistent mit der grafischen Windows-Benutzeroberfläche. Sie können auch benutzerdefinierte stream-Klassen ableiten, die direkt mit der Windows-Umgebung interagieren.

## <a name="see-also"></a>Siehe auch

[What a Stream Is (Was ist ein Stream?)](../standard-library/what-a-stream-is.md)
