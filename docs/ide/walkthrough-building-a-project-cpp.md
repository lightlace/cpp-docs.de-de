---
title: 'Exemplarische Vorgehensweise: Erstellen eines Projekts (C++)'
ms.date: 09/14/2018
helpviewer_keywords:
- building projects [C++]
- projects [C++], building
- project building [C++]
ms.assetid: d459bc03-88ef-48d0-9f9a-82d17f0b6a4d
ms.openlocfilehash: c12cd50dd92e728c88945cd83029f7e5e62816da
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2018
ms.locfileid: "51524156"
---
# <a name="walkthrough-building-a-project-c"></a>Exemplarische Vorgehensweise: Erstellen eines Projekts (C++)

In dieser exemplarischen Vorgehensweise fügen Sie absichtlich einen Visual C++-Syntaxfehler in den Code ein, um zu lernen, wie ein Kompilierungsfehler aussieht und wie Sie diesen beheben. Beim Kompilieren des Projekts wird eine Fehlermeldung angezeigt. Diese gibt an, worin das Problem besteht und wo es aufgetreten ist.

## <a name="prerequisites"></a>Erforderliche Komponenten

- In dieser exemplarischen Vorgehensweise wird davon ausgegangen, dass Sie die Grundlagen der Programmiersprache C++ beherrschen.

- Es wird ebenfalls davon ausgegangen, dass Sie die früheren exemplarischen Vorgehensweisen abgeschlossen haben, die unter [Verwenden der Visual Studio-IDE für die C++-Desktopentwicklung](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md) aufgeführt sind.

### <a name="to-fix-compilation-errors"></a>So beheben Sie Kompilierungsfehler

1. Löschen Sie das Semikolon in der letzten Zeile von „Games.cpp“, sodass diese Zeile ungefähr wie die folgende Anweisung aussieht:

   `return 0`

1. Wählen Sie auf der Menüleiste **Erstellen** > **Projektmappe erstellen** aus.

1. Eine Meldung im Fenster **Fehlerliste** gibt an, dass bei der Erstellung des Projekts ein Fehler aufgetreten ist. Die Beschreibung sieht in etwa wie die folgende Fehlermeldung aus:

   `error C2143: syntax error: missing ';' before '}'`

   Markieren Sie einen Fehler im Fenster **Fehlerliste**, und drücken Sie die Taste **F1**, um Hilfeinformationen anzuzeigen.

1. Fügen Sie das Semikolon wieder am Ende der Zeile mit dem Syntaxfehler ein:

   `return 0;`

1. Wählen Sie auf der Menüleiste **Erstellen** > **Projektmappe erstellen** aus.

   Die im Fenster **Ausgabe** angezeigte Meldung gibt an, dass das Projekt ordnungsgemäß kompiliert wurde.

    ```Output
    1>------ Build started: Project: Game, Configuration: Debug Win32 ------
    1>Game.cpp
    1>Game.vcxproj -> C:\Users\<username>\source\repos\Game\Debug\Game.exe
    ========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
    ```

## <a name="next-steps"></a>Nächste Schritte

**Zurück:** [Exemplarische Vorgehensweise: Arbeiten mit Projekten und Projektmappen (C++)](../ide/walkthrough-working-with-projects-and-solutions-cpp.md)<br/>
**Weiter:** [Exemplarische Vorgehensweise: Testen eines Projekts (C++)](../ide/walkthrough-testing-a-project-cpp.md)<br/>

## <a name="see-also"></a>Siehe auch

[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)<br/>
[Erstellen von C/C++-Programmen](../build/building-c-cpp-programs.md)<br/>
