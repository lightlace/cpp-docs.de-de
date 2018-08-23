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
ms.openlocfilehash: d5beaab3fe1642b3988e9d0dcbf258eab02e26b7
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42610308"
---
# <a name="mbcs-programming-tips"></a>Tipps für die MBCS-Programmierung
Verwenden Sie bei Neuentwicklungen für alle Zeichenfolgen, die die Endbenutzer möglicherweise sehen können, die Unicode-Zeichencodierung. MBCS ist eine Legacytechnologie, die durch Unicode ersetzt wurde. Dieser Abschnitt enthält Tipps für Entwickler, die vorhandene Programme verwalten müssen, die MBCS verwenden und für die eine Konvertierung in Unicode nicht sinnvoll ist. Die Hinweise beziehen sich sowohl auf MFC-Anwendungen als auch auf Anwendungen, die ohne MFC geschrieben werden. Folgende Themen werden behandelt:  
  
-   [Allgemeine Ratschläge für die MBCS-Programmierung](../text/general-mbcs-programming-advice.md)  
  
-   [Inkrementieren und Dekrementieren von Zeigern](../text/incrementing-and-decrementing-pointers.md)  
  
-   [Byte-Indizes](../text/byte-indices.md)  
  
-   [Letztes Zeichen einer Zeichenfolge](../text/last-character-in-a-string.md)  
  
-   [Zeichenzuweisungen](../text/character-assignment.md)  
  
-   [Zeichenvergleich](../text/character-comparison.md)  
  
-   [Pufferüberlauf](../text/buffer-overflow.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Unterstützung von Multibyte-Zeichensätzen (MBCS)](../text/support-for-multibyte-character-sets-mbcss.md)