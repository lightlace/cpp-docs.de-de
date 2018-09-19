---
title: Linkertoolwarnung Lnk4075 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4075
dev_langs:
- C++
helpviewer_keywords:
- LNK4075
ms.assetid: f39ad3f9-c263-4cf0-9d70-259fc56ac96d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1a021a9345975dcb197ab578901baf22f76db846
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46059653"
---
# <a name="linker-tools-warning-lnk4075"></a>Linkertoolwarnung LNK4075

ignorieren die Option "1" aufgrund von "option2" Spezifikation

Die zweite Option überschrieben.

Sich gegenseitig ausschließende Linkeroptionen werden angegeben wird.  Überprüfen Sie Ihre Optionen des Linkers.  Wobei die Optionen des Linkers angegeben werden, hängt davon ab, wie Sie Ihr Projekt erstellen.

- Wenn Sie in der Entwicklungsumgebung erstellen, sehen Sie den Linker-Eigenschaftenseiten für Ihr Projekt, und finden Sie unter, in denen beide Optionen des Linkers angegeben werden.  Finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md) für Weitere Informationen.

- Wenn Sie in der Befehlszeile erstellen, betrachten Sie die dort angegebenen Optionen des Linkers.

- Wenn Sie mit Buildskripts erstellen, Durchsuchen Sie Ihre Skripts angezeigt, in dem diese Optionen des Linkers angegeben werden.

Wenn Sie feststellen, wo sich gegenseitig ausschließende Linkeroptionen angegeben sind, entfernen Sie eine der Linkeroptionen verfügbar.

Einige spezifische Beispiele:

- Wenn Sie ein Modul, die Kompilierung Verknüpfen mit **"/ Zi"**, was bedeutet, dass eine interne Linkeroption EDITANDCONTINUE und ein kompiliertes Modul wurde mit/OPT: REF, / OPT: ICF oder/INCREMENTAL: No, das keine/EDITANDCONTINUE aufgerufen wird, werden Sie LNK4075 zu erhalten.  Finden Sie unter [/Z7, / Zi, / Zi (Debuginformationsformat)](../../build/reference/z7-zi-zi-debug-information-format.md) für Weitere Informationen.