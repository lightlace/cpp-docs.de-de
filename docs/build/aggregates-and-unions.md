---
title: Aggregate und Unions
ms.date: 11/04/2016
helpviewer_keywords:
- aggregates [C++], and unions
ms.assetid: 859fc211-b111-4f12-af98-de78e48f9b92
ms.openlocfilehash: a4206a5e07c765e9c789eab5c8963c9db4c2f234
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50496254"
---
# <a name="aggregates-and-unions"></a>Aggregate und Unions

Andere Typen wie Arrays, Strukturen und Unions, gelten strengere Ausrichtung, die die konsistente aggregieren und union-Speicher und Datenabruf zu gewährleisten. Hier sind die Definitionen für Arrays, Struktur und Union:

- Array

   Enthält eine geordnete Gruppe von benachbarten Datenobjekten. Jedes Objekt wird ein Element aufgerufen werden. Alle Elemente in einem Array haben die gleiche Größe und Datentyp.

- Struktur

   Enthält eine geordnete Gruppe von Datenobjekten. Im Gegensatz zu den Elementen eines Arrays können die Datenobjekte in einer Struktur unterschiedlichen Typen und Größen haben. Jedes Datenobjekt in einer Struktur wird als Member bezeichnet.

- Union

   Ein Objekt, das eine benannte Elemente enthält. Die Elemente der benannten Menge können einen beliebigen Typ sein. Der Speicher zugewiesen werden, damit eine Union ist der Speicherbedarf für den größten Member dieser Union zuzüglich möglicher Abstände, die erforderlich sind, für die Ausrichtung gleich.

Die folgende Tabelle zeigt die empfohlene Ausrichtung für die skalaren Member von Unions und Strukturen.

||||
|-|-|-|
|Skalaren Typ|C-Datentyp|Erforderlichen Ausrichtung ergibt|
|**INT8**|**char**|Byte|
|**UINT8**|**unsigned char**|Byte|
|**INT16**|**short**|Word|
|**UINT16**|**unsigned short**|Word|
|**INT32**|**Int**, **lange**|Zeigt Doppelwort|
|**UINT32**|**ganze Zahl ohne Vorzeichen, unsigned long**|Zeigt Doppelwort|
|**INT64**|**__int64**|Vierfachwort|
|**UINT64**|**__int64 ohne Vorzeichen**|Vierfachwort|
|**FP32-Vorgänge (einfache Genauigkeit)**|**float**|Zeigt Doppelwort|
|**FP64 (doppelte Genauigkeit)**|**double**|Vierfachwort|
|**ZEIGER**|<strong>\*</strong>|Vierfachwort|
|**__m64**|**Struktur __m64**|Vierfachwort|
|**__m128**|**Struktur __m128**|Octaword|

Die folgenden aggregierten Ausrichtung Regeln gelten:

- Die Ausrichtung eines Arrays ist identisch mit die Ausrichtung eines der Elemente des Arrays.

- Die Ausrichtung des Anfangs einer Struktur oder Union ist die maximale Ausrichtung eines einzelnen Member. Jedes Element in der Struktur oder Union muss korrekt ausgerichtet platziert werden, gemäß der vorstehenden Tabelle ist möglicherweise eine implizite interne Abstände, je nachdem das vorherige Element erforderlich.

- Die Größe der Struktur muss ein ganzzahliges Vielfaches seiner Ausrichtung Abstand hinter das letzte Element ist möglicherweise erforderlich. Da Strukturen und Unions in Arrays gruppiert werden können, muss jedes Arrayelement eine Struktur oder Union beginnen und enden auf die richtige Ausrichtung, die zuvor ermittelt.

- Es ist möglich, Ausrichten von Daten in so, dass der ausrichtungsanforderungen größer sein, solange alle zuvor genannten Regeln verwaltet werden.

- Ein einzelner Compiler kann die Komprimierung einer Struktur aus Gründen der Größe anpassen. Z. B. [/Zp (Strukturmemberausrichtung)](../build/reference/zp-struct-member-alignment.md) ermöglicht das Anpassen der Komprimierung von Strukturen.

## <a name="see-also"></a>Siehe auch

[Typen und Speicher](../build/types-and-storage.md)
