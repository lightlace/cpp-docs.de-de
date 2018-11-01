---
title: Linkertoolwarnung LNK4070
ms.date: 11/04/2016
f1_keywords:
- LNK4070
helpviewer_keywords:
- LNK4070
ms.assetid: f95f179a-fff9-427e-bd51-466b3934517f
ms.openlocfilehash: e7139b21f053ea8633356c7194cd719a6a4aef35
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50622975"
---
# <a name="linker-tools-warning-lnk4070"></a>Linkertoolwarnung LNK4070

-Direktive in/out: Dateiname. EXP weicht vom Ausgabedateinamen 'Dateiname'; Direktive wird ignoriert

Die `filename` Angabe in der [Namen](../../build/reference/name-c-cpp.md) oder [Bibliothek](../../build/reference/library.md) -Anweisung, wenn die EXP-Datei erstellt wurde, unterscheidet sich von der Ausgabe `filename` , entweder standardmäßig oder mit der angegebenwurde[/OUT](../../build/reference/out-output-file-name.md) Option.

Sie sehen diese Warnung, wenn Sie ändern den Namen der Ausgabedatei in der Entwicklungsumgebung und, in der DEF-Datei des Projekts nicht aktualisiert wurde. Manuell aktualisieren Sie, die DEF-Datei, um diese Warnung zu beheben.

Ein Clientprogramm, das die resultierende DLL verwendet, kann Probleme auftreten.