---
title: / ZF (schneller PDB Generation) | Microsoft Docs
ms.date: 02/22/2018
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- /Zf
dev_langs:
- C++
helpviewer_keywords:
- /Zf
- -Zf
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7012777643f993c552f79b58a02d4806c0ce4caa
ms.sourcegitcommit: c770a343def04ae77522708387c3f7c470e49969
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2018
---
# <a name="zf-faster-pdb-generation"></a>/ ZF (schneller PDB Generation)

Aktivieren Sie schnellere PDB-Generierung, bei der parallelen Builderstellung durch Minimierung der RPC-Aufrufe von mspdbsrv.exe.

## <a name="syntax"></a>Syntax

> **/Zf**

## <a name="remarks"></a>Hinweise

Die **/ZF** Option ermöglicht die compilerunterstützung für schnellere Erstellung von PDB-Dateien, bei Verwendung der [/MP (erstellen mit mehreren Prozessen)](mp-build-with-multiple-processes.md) Option, oder wenn das Buildsystem (z. B. [MSBuild ](/visualstudio/msbuild/msbuild-reference) oder [CMake](../../ide/cmake-tools-for-visual-cpp.md)) möglicherweise führen mehrere cl.exe Compiler Prozesse zur gleichen Zeit. Diese Option bewirkt, dass Compiler-front-End für die Generierung von Typindizes für jeden Typ Datensatz in der PDB-Datei bis zum Ende der Kompilierung zu verzögern, und fordert sie alle in einem einzelnen RPC-Aufruf mspdbsrv.exe, anstatt eine RPC-Anforderung für jeden Datensatz. Dies kann Build Durchsatz wesentlich verbessern, indem Sie verringert die RPC-Last auf den Prozess mspdbsrv.exe in einer Umgebung, in denen mehrere cl.exe-Compiler Prozesse gleichzeitig ausgeführt.

Da die **/ZF** Option gilt nur für die PDB-Datei generieren, erfordert die [/Zi](z7-zi-zi-debug-information-format.md) oder [/Zi](z7-zi-zi-debug-information-format.md) Option.

Die **/ZF** Option wird in Visual Studio 2017 Version 15.1 ab und ist standardmäßig deaktiviert.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Ändern der **Zusatzoptionen** Eigenschaft einschließen **/ZF** und wählen Sie dann **OK**.

## <a name="see-also"></a>Siehe auch

[Compileroptionen alphabetisch sortiert](compiler-options-listed-alphabetically.md)  
[/MP (Mit mehreren Prozessen erstellen)](mp-build-with-multiple-processes.md)  
