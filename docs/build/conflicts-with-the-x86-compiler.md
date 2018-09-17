---
title: Verursacht einen Konflikt mit der X86 Compiler | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 8e47f0d3-afe0-42d9-9efa-de239ddd3a05
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7f01e65adfb42a5fb3361e75ce34060f7dc1b9f9
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45709669"
---
# <a name="conflicts-with-the-x86-compiler"></a>Konflikt mit dem x86-Compiler

Datentypen, die größer als 4 Byte auf dem Stapel nicht automatisch ausgerichtet werden, bei der Verwendung der X86 Compiler zum Kompilieren einer Anwendung. Da die Architektur für die X86 Compiler kann ein 4-Byte-ausgerichtete-Stapel an, etwas größer als 4 Bytes, z. B. eine 64-Bit-Ganzzahl, kann nicht in eine 8-Byte-Adresse automatisch ausgerichtet werden.

Arbeiten mit einer nicht ausgerichteten Daten hat zwei Auswirkungen.

- Es dauert möglicherweise länger, nicht ausgerichtete Speicherorte zuzugreifen, als auf ausgerichtete.

- Nicht ausgerichtete Speicherorte können nicht in interlocked-Vorgänge verwendet werden.

Wenn Sie eine strengere Ausrichtung benötigen, verwenden Sie `__declspec(align(N)) on your variable declarations`. Dies bewirkt, dass den Compiler an, dass dynamisch im Stapel, um Ihren Spezifikationen zu erfüllen. Allerdings kann die dynamische Anpassung des Stapels zur Laufzeit langsamer Ausführung der Anwendung führen.

## <a name="see-also"></a>Siehe auch

[Typen und Speicher](../build/types-and-storage.md)<br/>
[align](../cpp/align-cpp.md)