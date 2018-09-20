---
title: Tipps für die MBCS-Programmierung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- _mbcs
dev_langs:
- C++
helpviewer_keywords:
- programming [C++], MBCS
- character sets [C++], multibyte
- MBCS [C++], programming
- multibyte characters [C++]
ms.assetid: d8ad36b8-917f-474e-8adb-69462adecd17
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ac4ed378640942dbe33490d618cec7289125b0c8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418787"
---
# <a name="mbcs-programming-tips"></a>Tipps für die MBCS-Programmierung

Verwenden Sie bei Neuentwicklungen für alle Zeichenfolgen, die die Endbenutzer möglicherweise sehen können, die Unicode-Zeichencodierung. MBCS ist eine Legacytechnologie, die durch Unicode ersetzt wurde. Dieser Abschnitt enthält Tipps für Entwickler, die vorhandene Programme verwalten müssen, die MBCS verwenden und für die eine Konvertierung in Unicode nicht sinnvoll ist. Die Hinweise beziehen sich sowohl auf MFC-Anwendungen als auch auf Anwendungen, die ohne MFC geschrieben werden. Folgende Themen werden behandelt:

- [Allgemeine Ratschläge für die MBCS-Programmierung](../text/general-mbcs-programming-advice.md)

- [Inkrementieren und Dekrementieren von Zeigern](../text/incrementing-and-decrementing-pointers.md)

- [Byte-Indizes](../text/byte-indices.md)

- [Letztes Zeichen einer Zeichenfolge](../text/last-character-in-a-string.md)

- [Zeichenzuweisungen](../text/character-assignment.md)

- [Zeichenvergleich](../text/character-comparison.md)

- [Pufferüberlauf](../text/buffer-overflow.md)

## <a name="see-also"></a>Siehe auch

[Unterstützung von Multibyte-Zeichensätzen (MBCS)](../text/support-for-multibyte-character-sets-mbcss.md)