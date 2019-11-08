---
title: C/C++-Präprozessorreferenz
ms.date: 10/31/2019
helpviewer_keywords:
- preprocessor
- preprocessor, reference overview
ms.assetid: e4a52843-7016-4f6d-8b40-cb1ace18f805
ms.openlocfilehash: ef93f2cb98a033eed539ffc25559937b274d8a21
ms.sourcegitcommit: 2362d15b5eb18d27773c3f7522da3d0eed9e2571
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73754080"
---
# <a name="cc-preprocessor-reference"></a>C/C++-Präprozessorreferenz

Die *C/C++ Präprozessor-Referenz* erläutert den Präprozessor, wie er in Microsoft C/C++implementiert ist. Der Präprozessor führt vorbereitende Vorgänge für C- und C++-Dateien aus, bevor sie an den Compiler übergeben werden. Sie können den Präprozessor verwenden, um Code bedingt zu kompilieren, Dateien einzufügen, Kompilierzeit-Fehlermeldungen anzugeben und computerspezifische Regeln auf Codeabschnitte anzuwenden.

In Visual Studio 2019 ermöglicht die [/experimental: Preprocessor](../build/reference/experimental-preprocessor.md) -Compileroption eine neue Implementierung des Präprozessors. Die neue Implementierung wird noch ausgeführt und wird daher als experimentell angesehen. Er soll schließlich mit C99, C11 und c++ 20 konform sein. Weitere Informationen finden Sie unter [Übersicht über den experimentellen MSVC-Präprozessor](preprocessor-experimental-overview.md).

## <a name="in-this-section"></a>In diesem Abschnitt

[Präprozessor\](preprocessor.md)
Bietet eine Übersicht über die herkömmlichen und neuen experimentellen Präprozessoren.

[Präprozessordirektiven](../preprocessor/preprocessor-directives.md)\
Beschreibt die Anweisungen, die normalerweise verwendet werden, um das Ändern und Kompilieren von Quellprogrammen in unterschiedlichen Ausführungsumgebungen zu vereinfachen.

[Präprozessoroperatoren](../preprocessor/preprocessor-operators.md)\
Erläutert die vier präprozessorspezifischen Operatoren, die im Kontext der `#define`-Direktive verwendet werden.

[Vordefinierte Makros](../preprocessor/predefined-macros.md)\
Erläutert vordefinierte Makros, wie von ANSI und Microsoft C++ angegeben.

[Pragmas](../preprocessor/pragma-directives-and-the-pragma-keyword.md)\
Erläutert Pragmas, die jedem Compiler eine Möglichkeit bieten, computer- und betriebssystemspezifische Funktionen bereitzustellen und dabei die Gesamtkompatibilität mit anderen C- und C++-Programmiersprachen beizubehalten.

## <a name="related-sections"></a>Verwandte Abschnitte

[ C++ Sprachreferenz](../cpp/cpp-language-reference.md)\
Enthält Referenzmaterial für die Microsoft-Implementierung der Programmiersprache C++.

[C-Sprachreferenz](../c-language/c-language-reference.md)\
Enthält Referenzmaterial für die Microsoft-Implementierung der Programmiersprache C.

[C/C++ Build-Verweis](../build/reference/c-cpp-building-reference.md)\
Enthält Links zu Themen, in denen die Verwendung von Compiler- und Linkeroptionen erörtert wird.

[Visual Studio-Projekte C++ -](../build/creating-and-managing-visual-cpp-projects.md)\
Beschreibt die Benutzeroberfläche in Visual Studio, die Ihnen die Möglichkeit gibt, die Verzeichnisse festzulegen, die das Projektsystem durchsucht, um Dateien für das C++-Projekt zu suchen.
