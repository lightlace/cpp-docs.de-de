---
title: Linkertoolwarnung LNK4092 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4092
dev_langs:
- C++
helpviewer_keywords:
- LNK4092
ms.assetid: d569ec47-a338-40e1-940b-8a8061459acb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b9b47b347e11e640425bc7840a0f78a33e9e3b7e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46113421"
---
# <a name="linker-tools-warning-lnk4092"></a>Linkertoolwarnung LNK4092

der freigegebene schreibbare Abschnitt "Abschnitt" enthält umsetzungen; Image kann möglicherweise nicht ordnungsgemäß ausgeführt.

Der Linker gibt diese Warnung immer dann, wenn Sie einen gemeinsamen Abschnitt, der über ein potenziell ernste Problem hinweist.

Ist eine Möglichkeit zum Freigeben von Daten zwischen mehreren Prozessen markieren einen Abschnitt als "freigegeben". Markieren einen Abschnitt als freigegebener kann jedoch Probleme verursachen. Beispielsweise haben Sie eine DLL, die Deklarationen wie folgt in einem freigegebenen Datenabschnitt enthält:

```
int var = 1;
int *pvar = &var;
```

Der Linker kann nicht aufgelöst werden `pvar` , da der Wert hängt davon ab, in dem die DLL in den Arbeitsspeicher geladen wird, daher wird einen Datensatz für die Umsetzung in der DLL. Beim Laden der DLL in den Speicher und die Adresse des `var` aufgelöst werden kann und `pvar` zugewiesen. Wenn ein anderer Prozess dieselbe DLL jedoch nicht gleichzeitig geladen zu beheben, die Umsetzung für die Adresse des `var` wird aktualisiert, für den zweiten Prozess und Adressbereich des ersten Prozesses auf die falsche Adresse verweist.