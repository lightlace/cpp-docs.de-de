---
title: 'NMAKE: Schwerwiegender Fehler U1033 | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1033
dev_langs:
- C++
helpviewer_keywords:
- U1033
ms.assetid: c146f7b5-7d5c-4329-a522-28a648546016
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7492e5fd77f8e88b2191174f84c298c6166d8d89
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46066378"
---
# <a name="nmake-fatal-error-u1033"></a>NMAKE: Schwerwiegender Fehler U1033

Syntaxfehler: "String" Unerwarteter

Die Zeichenfolge ist nicht Teil der gültige Syntax für ein Makefile.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. Falls die schließende spitze Klammern (**<<**) für eine Inline-Datei an, die nicht am Anfang einer Zeile sind, tritt der folgende Fehler auf:

    ```
    syntax error : 'EOF' unexpected
    ```

1. Wenn eine Makrodefinition in das Makefile ein Gleichheitszeichen enthält (**=**) ohne einen vorangestellten Namen, oder wenn der Name definiert wird, wird ein Makro, das nicht erweitert, tritt der folgende Fehler auf:

    ```
    syntax error : '=' unexpected
    ```

1. Wenn das Semikolon (**;**) in einer Kommentarzeile in TOOLS. INI ist nicht am Anfang der Zeile, tritt der folgende Fehler auf:

    ```
    syntax error : ';' unexpected
    ```

1. Wenn das Makefile durch ein Textverarbeitungsprogramm formatiert wurde, kann der folgende Fehler auftreten:

    ```
    syntax error : ':' unexpected
    ```