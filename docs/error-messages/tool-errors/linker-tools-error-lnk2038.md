---
title: Linkertoolfehler LNK2038
ms.date: 12/15/2017
f1_keywords:
- LNK2038
helpviewer_keywords:
- LNK2038
ms.openlocfilehash: f2839494232e7b57325b6f7abb960a258ba13078
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2019
ms.locfileid: "65446955"
---
# <a name="linker-tools-error-lnk2038"></a>Linkertoolfehler LNK2038

> Konflikt erkannt, für die '*Namen*': Wert "*value_1*'Wert nicht übereinstimmen'*value_2*" in *filename.obj*

Ein Symbolkonflikt wurde vom Linker erkannt. Dieser Fehler zeigt an, die verschiedene Teile einer app für Bibliotheken oder ein anderes Objekt, dass die app-Links, verwenden Sie in Konflikt stehende Definitionen des Symbols codieren. Die [Ermitteln von Konflikten](../../preprocessor/detect-mismatch.md) Pragma wird verwendet, um diese Symbole zu definieren und ihre in Konflikt stehende Werte zu erkennen.

## <a name="possible-causes-and-solutions"></a>Mögliche Ursachen und Lösungen

Dieser Fehler kann auftreten, wenn eine Objektdatei im Projekt veraltet ist. Bevor Sie andere Lösungen zur Fehlerbehebung ausprobieren, versuchen Sie, einen bereinigten Build auszuführen, um sicherzustellen, dass die Objektdateien aktuell sind.

Visual Studio definiert die folgenden Symbole, um das Verknüpfen von nicht kompatiblem Code zu verhindern, der Laufzeitfehler oder anderes unerwartetes Verhalten verursachen kann.

- `_MSC_VER` Gibt die Haupt- und Nebenversionsnummern Versionsnummern von Microsoft C++ -Compiler (MSVC), der zum Erstellen einer app oder Bibliothek verwendet wird. Code, der kompiliert wird, mit einer Version von der MSVC ist inkompatibel mit Code, mit einer Version, die verschiedene Haupt- und Nebenversionsnummern Versionsnummern kompiliert wird. Weitere Informationen finden Sie unter `_MSC_VER` in [Predefined Macros](../../preprocessor/predefined-macros.md).

   Wenn Sie eine Bibliothek, die nicht mit der Version von der MSVC kompatibel, die Sie verwenden verweisen, und Sie nicht abrufen oder erstellen Sie eine kompatible Version der Bibliothek, können Sie eine frühere Version des Compilers verwenden, zum Erstellen Ihres Projekts: Ändern der  **Plattformtoolset** -Eigenschaft des Projekts auf das frühere Toolset. Weitere Informationen finden Sie unter [Vorgehensweise: Modify the Target Framework and Platform Toolset (Vorgehensweise: Ändern des Zielframeworks und des Plattformtoolsets)](../../build/how-to-modify-the-target-framework-and-platform-toolset.md).

- `_ITERATOR_DEBUG_LEVEL` Gibt die Ebene der Sicherheits- und Debugfunktionen, die in der C++-Standardbibliothek aktiviert werden. Diese Funktionen können die Darstellung bestimmter C++-Standardbibliotheksobjekte ändern. Dadurch werden diese möglicherweise mit solchen Objekten inkompatibel, die andere Sicherheits- und Debugfunktionen verwenden. Weitere Informationen finden Sie unter [_ITERATOR_DEBUG_LEVEL](../../standard-library/iterator-debug-level.md).

- `RuntimeLibrary` Gibt die Version der C++-Standardbibliothek und die C-Laufzeit, die von einer app oder Bibliothek verwendet wird. Code, der eine Version der C++-Standardbibliothek oder C-Laufzeit verwendet, ist nicht mit Code kompatibel, der eine andere Version verwendet. Weitere Informationen finden Sie unter [/MD, /MT, /LD (Laufzeitbibliothek verwenden)](../../build/reference/md-mt-ld-use-run-time-library.md).

- `_PPLTASKS_WITH_WINRT` Gibt an, Code, verwendet der [Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) verknüpft ist, um Objekte, die mit einer anderen Einstellung für die [/Zw](../../build/reference/zw-windows-runtime-compilation.md) -Compileroption. (**/Zw** unterstützt C++ / CX.) Code, der verwendet wird oder hängt von der PPL muss kompiliert werden, mit der gleichen **/Zw** Einstellung, die in der Rest der app verwendet wird.

Stellen Sie sicher, dass die Werte dieser Symbole für alle Projekte in der Visual Studio-Projektmappe konsistent sind, ebenso wie mit Code und Bibliotheken, mit denen die App verknüpft ist.

## <a name="third-party-library-issues-and-vcpkg"></a>Bibliotheken von Drittanbietern Probleme und Vcpkg

Wenn dieser Fehler angezeigt wird, wenn Sie eine Drittanbieter-Bibliothek als Teil Ihres Builds konfigurieren möchten, sollten Sie [Vcpkg](../../vcpkg.md), im Visual C++ Paket-Manager zum Installieren und erstellen Sie die Bibliothek. Vcpkg unterstützt eine große und wachsende [Liste der Drittanbieter-Bibliotheken](https://github.com/Microsoft/vcpkg/tree/master/ports), und legt alle Eigenschaften und Abhängigkeiten, die als Teil des Projekts für erfolgreiche Builds erforderlich sind. Weitere Informationen finden Sie im zugehörigen [Visual C++-Blog](https://blogs.msdn.microsoft.com/vcblog/2016/09/19/vcpkg-a-tool-to-acquire-and-build-c-open-source-libraries-on-windows/) Posten.

## <a name="see-also"></a>Siehe auch

[Fehler und Warnungen der Linkertools](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)