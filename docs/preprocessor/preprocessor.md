---
title: Präprozessor
ms.date: 08/29/2019
helpviewer_keywords:
- preprocessor
ms.assetid: e120eda3-b413-49f1-a07c-e9fb128cf500
ms.openlocfilehash: 883504810f1b659e28764a75ebc7cfda325920a5
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222233"
---
# <a name="preprocessor"></a>Präprozessor

Der Präprozessor ist ein Textprozessor, der den Text einer Quelldatei im Rahmen der ersten Übersetzungsphase bearbeitet. Der Quell Text wird vom Präprozessor nicht analysiert, er wird jedoch in Token aufgeteilt, um Makro Aufrufe zu suchen. Obwohl der Compiler den Präprozessor normalerweise im ersten Durchlauf aufruft, kann der Präprozessor auch separat aufgerufen werden, um Text ohne Kompilierung zu verarbeiten.

Das Referenzmaterial zum Präprozessor enthält die folgenden Abschnitte:

- [Präprozessordirektiven](../preprocessor/preprocessor-directives.md)

- [Präprozessoroperatoren](../preprocessor/preprocessor-operators.md)

- [Vordefinierte Makros](../preprocessor/predefined-macros.md)

- [Pragmas](../preprocessor/pragma-directives-and-the-pragma-keyword.md)

**Microsoft-spezifisch**

Sie können eine Auflistung Ihres Quellcodes nach der Vorverarbeitung abrufen, indem Sie die [/E](../build/reference/e-preprocess-to-stdout.md) -oder [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) -Compileroption verwenden. Beide Optionen rufen den Präprozessor auf und senden den resultierenden Text an das Standardausgabe Gerät, was in den meisten Fällen die Konsole ist. Der Unterschied zwischen den beiden Optionen besteht `/E` darin `#line` , dass- `/EP` Direktiven einschließt und diese Direktiven entfernt.

**Ende Microsoft-spezifisch**

##  <a name="_predir_special_terminology"></a>Besondere Terminologie

In der Präprozessordokumentation bezieht sich der Begriff "Argument" auf die Entität, die an eine Funktion übergeben wird. In einigen Fällen wird Sie durch "tatsächlich" oder "formal" geändert, wodurch der im Funktions Aufrufwert angegebene Argument Ausdruck und die Argument Deklaration, die in der Funktionsdefinition angegeben ist, beschrieben werden.

Der Begriff "Variable" bezeichnet ein einfaches C-Datenobjekt. Der Begriff "Object" bezieht sich auf C++ Objekte und Variablen. Es handelt sich um einen inklusiven Begriff.

## <a name="see-also"></a>Siehe auch

[C/C++ präprozessorverweis](../preprocessor/c-cpp-preprocessor-reference.md)\
[Phasen der Übersetzung](../preprocessor/phases-of-translation.md)
