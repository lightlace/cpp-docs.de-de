---
title: Linkertoolwarnung LNK4092
ms.date: 11/04/2016
f1_keywords:
- LNK4092
helpviewer_keywords:
- LNK4092
ms.assetid: d569ec47-a338-40e1-940b-8a8061459acb
ms.openlocfilehash: 0b18002135d225a90f7e45adc2ff57a64c0a79f4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50531025"
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