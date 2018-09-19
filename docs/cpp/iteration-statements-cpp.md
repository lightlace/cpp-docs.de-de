---
title: Iterationsanweisungen (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- iteration statements
- loop structures, iteration statements
ms.assetid: bf6d75f7-ead2-426a-9c47-33847f59b8c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 604534a30d9d6dfbc9cc38825413f98af5435cf6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46040647"
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