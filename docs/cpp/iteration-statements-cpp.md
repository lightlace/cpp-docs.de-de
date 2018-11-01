---
title: Iterationsanweisungen (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- iteration statements
- loop structures, iteration statements
ms.assetid: bf6d75f7-ead2-426a-9c47-33847f59b8c7
ms.openlocfilehash: 72f81e2fc58a31db0c4cd3f77ba182bd8b8152a4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50644937"
---
# <a name="iteration-statements-c"></a>Iterationsanweisungen (C++)

Iterationsanweisungen bewirken, dass Anweisungen (oder Verbundanweisungen) NULL mal oder mehrmals ausgeführt werden, je nach LOOP-Beendigungskriterien. Wenn diese Anweisungen verbundanweisungen sind, sie werden nacheinander ausgeführt, außer wenn entweder die [Break](../cpp/break-statement-cpp.md) Anweisung oder der [weiterhin](../cpp/continue-statement-cpp.md) -Anweisung gefunden.

C++ stellt vier iterationsanweisungen bereit – [während](../cpp/while-statement-cpp.md), [führen](../cpp/do-while-statement-cpp.md), [für](../cpp/for-statement-cpp.md), und [bereichsbasierte for](../cpp/range-based-for-statement-cpp.md). Jede dieser durchläuft, bis der beendigungsausdruck mit Null (False) ausgewertet wird oder bis die Beendigung der Schleife erzwungen wird, mit einer **Break** Anweisung. In der folgenden Tabelle werden diese Anweisungen und ihre Aktionen zusammengefasst. Jede von ihnen wird in den folgenden Abschnitten im Detail behandelt.

### <a name="iteration-statements"></a>Iterationsanweisungen

|Anweisung|Ausgewertet an|Initialisierung|Inkrement|
|---------------|------------------|--------------------|---------------|
|**while**|Anfang der Schleife|Nein|Nein|
|**do**|Ende der Schleife|Nein|Nein|
|**for**|Anfang der Schleife|Ja|Ja|
|**bereichsbasierte for**|Anfang der Schleife|Ja|Ja|

Der Anweisungsteil einer Iterationsanweisung kann keine Deklaration sein. Es kann jedoch eine Verbundanweisung sein, die eine Deklaration enthält.

## <a name="see-also"></a>Siehe auch

[Übersicht über C++-Anweisungen](../cpp/overview-of-cpp-statements.md)