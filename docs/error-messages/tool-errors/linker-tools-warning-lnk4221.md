---
title: Linkertoolwarnung LNK4221 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4221
dev_langs:
- C++
helpviewer_keywords:
- LNK4221
ms.assetid: 8e2eb2de-9532-4b85-908a-8c9ff5c4cccb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 921f3a563b465332408c112deca61faa01e26cac
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46032912"
---
# <a name="linker-tools-warning-lnk4221"></a>Linkertoolwarnung LNK4221

Die Objektdatei definiert kein zuvor undefinierten öffentlichen Symbole, damit er von keinem Verknüpfungsvorgang nicht verwendet werden, die diese Bibliothek benutzt.

Erwägen Sie die folgenden zwei Codeausschnitten.

```
// a.cpp
#include <atlbase.h>
```

```
// b.cpp
#include <atlbase.h>
int function()
{
   return 0;
}

```

Führen Sie zum Kompilieren Sie die Dateien, und erstellen zwei Objektdateien, **cl/c a.cpp b.cpp** an einer Eingabeaufforderung. Wenn Sie die Objektdateien mit verknüpfen **verknüpfen/lib-out: Test.lib a.obj b.obj**, erhalten Sie die LNK4221-Warnung. Wenn Sie die Objekte mit verknüpfen **verknüpfen/lib-out: Test.lib b.obj "a.obj"**, erhalten Sie eine Warnung nicht.

Im zweiten Szenario wird keine Warnung ausgegeben, da der Linker Weise eine hohe Last in First Out (LIFO) arbeitet. Im ersten Szenario b.obj wird verarbeitet, bevor "a.obj" und "a.obj" enthält keine neuen Symbole hinzufügen. Weist den Linker an, "a.obj" zuerst zu verarbeiten, können Sie die Warnung vermeiden.

Eine häufige Ursache für diesen Fehler ist beim Angeben von zwei Quelldateien enthalten der Option ["/ Yc" (Erstellen vorkompilierter Headerdatei)](../../build/reference/yc-create-precompiled-header-file.md) mit dem gleichen Headerdateinamen angegeben, der **vorkompilierter Header** Feld. Eine häufige Ursache für dieses Problem befasst sich mit "stdafx.h", da standardmäßig "stdafx.cpp", "stdafx.h" enthält, und neue Symbole werden nicht hinzugefügt. Wenn einer anderen Quelldatei "stdafx.h" mit enthält **"/ Yc"** und die zugehörigen OBJ-Datei wird verarbeitet, bevor "stdafx.obj" verwendet, löst der Linker LNK4221.

Eine Möglichkeit zum Beheben dieses Problems besteht darin sicherzustellen, dass für jeden vorkompilierten Header, besteht nur eine Quelldatei, die sie mit enthält **"/ Yc"**. Alle anderen Quelldateien müssen vorkompilierte Header verwenden. Weitere Informationen dazu, wie Sie diese Einstellung zu ändern, finden Sie unter [/Yu (vorkompilierte Headerdatei verwenden)](../../build/reference/yu-use-precompiled-header-file.md).