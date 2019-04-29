---
title: / ZF (schnellere PDB-Generierung)
ms.date: 03/29/2018
f1_keywords:
- /Zf
helpviewer_keywords:
- /Zf
- -Zf
ms.openlocfilehash: bed37a189e3eb1eb7b55dbdee1f81f360eafa721
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62315849"
---
# <a name="zf-faster-pdb-generation"></a>/ ZF (schnellere PDB-Generierung)

Aktivieren Sie schnellere PDB-Generierung in parallele Builds, indem Sie RPC-Aufrufe von mspdbsrv.exe minimieren.

## <a name="syntax"></a>Syntax

> **/Zf**

## <a name="remarks"></a>Hinweise

Die **/ZF** Option aktiviert die Unterstützung des Compilers für schnellere Erstellung der PDB-Dateien, bei Verwendung von der [/MP (erstellen mit mehreren Prozessen)](mp-build-with-multiple-processes.md) auswählen, oder wenn das Buildsystem (z. B. [MSBuild ](/visualstudio/msbuild/msbuild-reference) oder [CMake](../cmake-projects-in-visual-studio.md)) möglicherweise führen mehrere cl.exe Compiler Prozesse zur gleichen Zeit. Diese Option bewirkt, dass der Compiler-Front-End zu verzögern, Generierung von Typindizes für jeden Typ-Datensatz in die PDB-Datei bis zum Ende der Kompilierung und fordert dann diese alle an einem einzigen RPC-Aufruf von mspdbsrv.exe, anstatt eine RPC-Anforderung für jeden Datensatz. Dies kann Builddurchsatz erheblich verbessert werden durch Reduzieren der RPC-Last auf den mspdbsrv.exe-Prozess in einer Umgebung, in denen mehrere cl.exe-Compiler-Prozesse gleichzeitig ausgeführt.

Da die **/ZF** -Option gilt nur für PDB-Generierung, erfordert die ["/ Zi"](z7-zi-zi-debug-information-format.md) oder ["/ Zi"](z7-zi-zi-debug-information-format.md) Option.

Die **/ZF** Option ist verfügbar ab der in Visual Studio 2017 Version 15.1, ist es, in denen standardmäßig deaktiviert. Visual Studio 2017 Version 15.7 ab Preview 3, diese Option ist standardmäßig bei der **"/ Zi"** oder **"/ Zi"** aktiviert ist.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Ändern der **zusätzliche Optionen** Eigenschaft sollen **/ZF** und wählen Sie dann **OK**.

## <a name="see-also"></a>Siehe auch

[Compileroptionen alphabetisch sortiert](compiler-options-listed-alphabetically.md)<br/>
[/MP (Mit mehreren Prozessen erstellen)](mp-build-with-multiple-processes.md)<br/>
