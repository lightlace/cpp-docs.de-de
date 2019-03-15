---
title: /GL (Optimierung des ganzen Programms)
ms.date: 11/04/2016
f1_keywords:
- /gl
- VC.Project.VCCLWCECompilerTool.WholeProgramOptimization
helpviewer_keywords:
- /GL compiler option [C++]
- whole program optimizations and C++ compiler
- -GL compiler option [C++]
- GL compiler option [C++]
ms.assetid: 09d51e2d-9728-4bd0-b5dc-3b8284aca1d1
ms.openlocfilehash: 6251209dac74a504bb0635f0c544c39935090a42
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57812381"
---
# <a name="gl-whole-program-optimization"></a>/GL (Optimierung des ganzen Programms)

Aktiviert die Optimierung des gesamten Programms.

## <a name="syntax"></a>Syntax

```
/GL[-]
```

## <a name="remarks"></a>Hinweise

Optimierung des ganzen Programms kann der Compiler Optimierungen mit Informationen zu allen Modulen im Programm auszuführen. Ohne Optimierung des ganzen Programms, Optimierungen ausgeführt werden, auf einer pro Modul (Kompiliereinheit).

Optimierung des ganzen Programms ist standardmäßig deaktiviert und muss explizit aktiviert werden kann. Es ist jedoch auch möglich, explizit mit deaktivieren **/GL-**.

Mit Informationen zu allen Modulen können der Compiler:

- Optimieren Sie die Verwendung von Registern über Grenzen hinweg.

- Tun Sie besser nachverfolgen von Änderungen an globalen Daten, sodass eine Reduzierung der Anzahl von Lade- und Speichervorgänge.

- Führen Sie eine besser verfolgen, die die mögliche Sätze von Elementen, die geändert, indem ein Zeiger zu dereferenzieren, verringert die Anzahl von Lade- und Speichervorgänge.

- Inlineersetzung von Funktionen in einem Modul auch, wenn die Funktion in einem anderen Modul definiert ist.

erstellte OBJ-Dateien mit **"/ GL"** wird nicht als solche Linker-Dienstprogramme [EDITBIN](editbin-reference.md) und [DUMPBIN](dumpbin-reference.md).

Wenn Sie das Programm mit Kompilieren **"/ GL"** und [/c](c-compile-without-linking.md), sollten Sie die Linkeroption "/ LTCG" verwenden, um die Ausgabedatei zu erstellen.

["/ Zi"](z7-zi-zi-debug-information-format.md) kann nicht verwendet werden, mit **"/ GL"**

Das Format der Dateien mit erzeugten **"/ GL"** in der aktuellen Version möglicherweise nicht von nachfolgenden Versionen von Visual C++ gelesen werden. Sie sollten eine LIB-Datei besteht aus der OBJ-Dateien, die mit erzeugt wurden nicht senden **"/ GL"** , wenn Sie bereit für den Versand von Kopien der LIB-Datei für alle Versionen von Visual C++ sind Sie erwarten Ihre Benutzer verwenden, jetzt und in der Zukunft.

erstellte OBJ-Dateien mit **"/ GL"** vorkompilierten Headerdateien sollte nicht verwendet werden, um eine LIB-Datei zu erstellen, es sei denn, die LIB-Datei auf dem gleichen Computer verknüpft wird, die erstellt, und die **"/ GL"** OBJ-Datei. Zum Zeitpunkt der Verknüpfung werden Informationen aus der OBJ-Datei der vorkompilierten Headerdatei benötigt.

Weitere Informationen zu den Optimierungen mit verfügbar und die Einschränkungen der Optimierung des ganzen Programms, finden Sie unter ["/ LTCG"](ltcg-link-time-code-generation.md).  **"/ GL"** Außerdem macht geführte Optimierung verfügbar sind, finden Sie unter "/ LTCG".  Beim Kompilieren für Profilgesteuerte Optimierungen und Funktion, die Reihenfolge von Ihrem Profilgesteuerte Optimierungen werden soll, muss der Kompilierung mit [/Gy](gy-enable-function-level-linking.md) oder eine Compileroption, die/Gy impliziert.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Finden Sie unter [/LTCG (Link-Time Code Generation)](ltcg-link-time-code-generation.md) Informationen zum angeben **"/ GL"** in der Entwicklungsumgebung.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

1. Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WholeProgramOptimization%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Compiler-Optionen](compiler-options.md)<br/>
[MSVC-Compiler-Befehlszeilensyntax](compiler-command-line-syntax.md)
