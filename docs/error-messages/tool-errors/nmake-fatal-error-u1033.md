---
title: 'NMAKE: Schwerwiegender Fehler U1033'
ms.date: 11/04/2016
f1_keywords:
- U1033
helpviewer_keywords:
- U1033
ms.assetid: c146f7b5-7d5c-4329-a522-28a648546016
ms.openlocfilehash: 3b1df28e3cd7b27a9e7a130d9d71c1af68db9aec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50445239"
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