---
title: Linkertoolwarnung LNK4070 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4070
dev_langs:
- C++
helpviewer_keywords:
- LNK4070
ms.assetid: f95f179a-fff9-427e-bd51-466b3934517f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9cfb4ae1c5440742c491d9615a2b4929a9b04f66
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106945"
---
# <a name="linker-tools-warning-lnk4070"></a>Linkertoolwarnung LNK4070

-Direktive in/out: Dateiname. EXP weicht vom Ausgabedateinamen 'Dateiname'; Direktive wird ignoriert

Die `filename` Angabe in der [Namen](../../build/reference/name-c-cpp.md) oder [Bibliothek](../../build/reference/library.md) -Anweisung, wenn die EXP-Datei erstellt wurde, unterscheidet sich von der Ausgabe `filename` , entweder standardmäßig oder mit der angegebenwurde[/OUT](../../build/reference/out-output-file-name.md) Option.

Sie sehen diese Warnung, wenn Sie ändern den Namen der Ausgabedatei in der Entwicklungsumgebung und, in der DEF-Datei des Projekts nicht aktualisiert wurde. Manuell aktualisieren Sie, die DEF-Datei, um diese Warnung zu beheben.

Ein Clientprogramm, das die resultierende DLL verwendet, kann Probleme auftreten.