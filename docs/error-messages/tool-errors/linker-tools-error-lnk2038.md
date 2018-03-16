---
title: Linkertoolfehler Lnk2038 | Microsoft Docs
ms.custom: 
ms.date: 12/15/2017
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK2038
dev_langs:
- C++
helpviewer_keywords:
- LNK2038
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 13f65f403cac43551b787abab15713fb9ffab618
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2018
---
# <a name="linker-tools-error-lnk2038"></a>Linkertoolfehler LNK2038

> Konflikt erkannt, für die "*Namen*": Wert "*value_1*'Wert nicht übereinstimmen'*value_2*" in *filename.obj*

Ein Symbolkonflikt wurde vom Linker erkannt. Dieser Fehler zeigt an, dass unterschiedliche Teile einer app, einschließlich Bibliotheken oder ein anderes Objekt code verfügen, der die app-Links zu verwenden, in Konflikt stehende Definitionen des Symbols. Die [Konflikt erkennen](../../preprocessor/detect-mismatch.md) Pragma wird verwendet, um diese Symbole zu definieren und ihre in Konflikt stehenden Werte zu erkennen.

## <a name="possible-causes-and-solutions"></a>Mögliche Ursachen und Lösungen

Dieser Fehler kann auftreten, wenn eine Objektdatei im Projekt veraltet ist. Bevor Sie andere Lösungen zur Fehlerbehebung ausprobieren, versuchen Sie, einen bereinigten Build auszuführen, um sicherzustellen, dass die Objektdateien aktuell sind.

Visual Studio definiert die folgenden Symbole, um das Verknüpfen von nicht kompatiblem Code zu verhindern, der Laufzeitfehler oder anderes unerwartetes Verhalten verursachen kann.

- `_MSC_VER`  
   Gibt die Haupt- und Nebenversionsnummern des Visual C++-Compilers an, der verwendet wird, um eine App oder eine Bibliothek zu erstellen. Code, der mit einer Version des Visual C++-Compilers kompiliert wird, ist nicht mit Code kompatibel, der mit einer Version kompiliert wird, die andere Haupt- und Nebenversionsnummern hat. Weitere Informationen finden Sie unter `_MSC_VER` in [vordefinierte Makros](../../preprocessor/predefined-macros.md).

   Wenn Sie in einer Bibliothek, die nicht mit der Version des Visual C++-Compilers kompatibel, die Sie verwenden verknüpfen, und Sie nicht erworben oder eine kompatible Version der Bibliothek zu erstellen, können Sie eine frühere Version des Compilers verwenden, zum Erstellen des Projekts: Ändern der <C1/>Plattformtoolset** Eigenschaft des Projekts, um die früheren Toolset. Weitere Informationen finden Sie unter [Vorgehensweise: Ändern des Zielframeworks und Plattformtoolset](../../build/how-to-modify-the-target-framework-and-platform-toolset.md).

- `_ITERATOR_DEBUG_LEVEL`  
   Gibt die Ebene der Sicherheits- und Debugfunktionen an, die in der C++-Standardbibliothek aktiviert werden. Diese Funktionen können die Darstellung bestimmter C++-Standardbibliotheksobjekte ändern. Dadurch werden diese möglicherweise mit solchen Objekten inkompatibel, die andere Sicherheits- und Debugfunktionen verwenden. Weitere Informationen finden Sie unter [_ITERATOR_DEBUG_LEVEL](../../standard-library/iterator-debug-level.md).

- `RuntimeLibrary`  
   Gibt die Version der C++-Standardbibliothek und der C-Laufzeit an, die von einer App oder einer Bibliothek verwendet wird. Code, der eine Version der C++-Standardbibliothek oder C-Laufzeit verwendet, ist nicht mit Code kompatibel, der eine andere Version verwendet. Weitere Informationen finden Sie unter [/MD, /MT, /LD (Laufzeitbibliothek verwenden)](../../build/reference/md-mt-ld-use-run-time-library.md).

- `_PPLTASKS_WITH_WINRT`  
   Gibt an, Code, der verwendet die [Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) mit Objekten, die mit einer anderen Einstellung für kompiliert verlinkt wird die [/Zw](../../build/reference/zw-windows-runtime-compilation.md) -Compileroption. (**/Zw** unterstützt C + c++ / CX.) Code, der verwendet wird oder hängt von der PPL muss kompiliert werden, mithilfe der gleichen **/Zw** Einstellung, die in den Rest der app verwendet wird.

Stellen Sie sicher, dass die Werte dieser Symbole für alle Projekte in der Visual Studio-Projektmappe konsistent sind, ebenso wie mit Code und Bibliotheken, mit denen die App verknüpft ist.

## <a name="third-party-library-issues-and-vcpkg"></a>Drittanbieter-Bibliothek Probleme und Vcpkg

Wenn dieser Fehler angezeigt, wenn Sie eine Bibliothek eines Drittanbieters als Teil Ihres Builds konfigurieren möchten, erwägen Sie [Vcpkg](../../vcpkg.md), die Visual C++ Paket-Manager, zum Installieren und die Bibliothek erstellen. Vcpkg unterstützt eine große und wachsende [Liste der Bibliotheken von Drittanbietern](https://github.com/Microsoft/vcpkg/tree/master/ports), und legt alle Konfigurationseigenschaften und Abhängigkeiten für erfolgreiche Builds, die als Teil Ihres Projekts erforderlich sind. Weitere Informationen finden Sie unter den zugehörigen [Visual C++-Blog](https://blogs.msdn.microsoft.com/vcblog/2016/09/19/vcpkg-a-tool-to-acquire-and-build-c-open-source-libraries-on-windows/) bereitstellen.

## <a name="see-also"></a>Siehe auch

[Fehler und Warnungen der Linkertools](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)