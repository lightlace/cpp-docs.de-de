---
title: Eingabe-/Ausgabealternativen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- I/O [C++], alternatives
ms.assetid: 9f8401c7-d90d-4285-8918-63573df74a80
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 28e61dbbd7db6737cd39337acc9925c669cff61d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="inputoutput-alternatives"></a>Eingabe-/Ausgabealternativen

Visual C++ stellt mehrere Alternativen für die E/A-Programmierung bereit:

- Direkte C-Laufzeitbibliothek, ungepufferte E/A.

- ANSI C-Laufzeitbibliotheksstream E/A.

- Direkte Konsole und Port-E/A.

- Microsoft Foundation Class-Bibliothek.

- Microsoft C++ Standardbibliothek.

Die iostream-Klassen sind für gepufferten, formatierten Text E/A nützlich. Sie sind auch für ungepufferte oder binäre E/A nützlich, wenn Sie eine C++-Programmierschnittstelle benötigen und nicht die Microsoft Foundation Class (MFC)-Bibliothek verwenden möchten. Die iostream-Klassen sind eine objektorientierte E/A-Alternative zu den C-Laufzeitfunktionen.

Sie können die iostream-Klassen mit dem Microsoft Windows-Betriebssystem verwenden. Zeichenfolgen- und Dateistreams arbeiten ohne Einschränkungen, aber die Streamobjekte im Zeichenmodus `cin`, `cout`, `cerr`, und `clog` sind inkonsistent mit der grafischen Windows-Benutzeroberfläche. Sie können auch benutzerdefinierte stream-Klassen ableiten, die direkt mit der Windows-Umgebung interagieren.

## <a name="see-also"></a>Siehe auch

[What a Stream Is (Was ist ein Stream?)](../standard-library/what-a-stream-is.md)<br/>
