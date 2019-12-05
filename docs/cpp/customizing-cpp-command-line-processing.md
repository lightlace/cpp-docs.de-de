---
title: Anpassen der C++-Befehlszeilenverarbeitung
ms.date: 11/04/2016
f1_keywords:
- _setenvp
- _setargv
helpviewer_keywords:
- command line [C++], processing
- command-line processing
- startup code, customizing command-line processing
- environment, environment-processing routine
- _setargv function
- command line [C++], processing arguments
- suppressing environment processing
- _setenvp function
ms.assetid: aae01cbb-892b-48b8-8e1f-34f22421f263
ms.openlocfilehash: 1541840521695658b5c4d809ba7e11767b1330a2
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857553"
---
# <a name="customizing-c-command-line-processing"></a>Anpassen der C++-Befehlszeilenverarbeitung

**Microsoft-spezifisch**

Wenn das Programm keine Befehlszeilenargumente akzeptiert, können Sie ein wenig Platz sparen, indem Sie die Verwendung der Bibliotheksroutine unterdrücken, die die Befehlszeilenverarbeitung ausführt. Diese Routine wird `_setargv` aufgerufen und unter Platzhalter [Erweiterung](../cpp/wildcard-expansion.md)beschrieben. Um die Verwendung zu unterdrücken, definieren Sie eine Routine, die in der Datei mit der `main`-Funktion keine Aktion ausführt, und benennen Sie Sie `_setargv`. Der `_setargv`-wird dann durch die Definition von `_setargv`erfüllt, und die Bibliotheksversion wird nicht geladen.

Wenn Sie auf die Umgebungs Tabelle nicht über das `envp`-Argument zugreifen, können Sie auch eine eigene leere Routine bereitstellen, die anstelle von `_setenvp`, der Umgebungs Verarbeitungsroutine, verwendet werden soll. Genau wie bei der `_setargv`-Funktion müssen `_setenvp` als **extern "C"** deklariert werden.

Das Programm kann in der C-Lauf Zeit Bibliothek Aufrufe an die `spawn` oder `exec` Familie von Routinen tätigen. Wenn dies der Fall ist, sollten Sie die umgebungsverarbeitende Routine nicht unterdrücken, da diese Routine verwendet wird, um eine Umgebung aus dem übergeordneten Prozess an den untergeordneten Prozess zu übergeben.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[main: Programmstart](../cpp/main-program-startup.md)