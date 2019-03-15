---
title: /c (Kompilieren ohne Verknüpfen)
ms.date: 11/04/2016
f1_keywords:
- /c
helpviewer_keywords:
- suppress link
- cl.exe compiler, compiling without linking
- -c compiler option [C++]
- c compiler option [C++]
- /c compiler option [C++]
ms.assetid: 8017fc3d-e5dd-4668-a1f7-3120daa95d20
ms.openlocfilehash: bfe351daf43b913f10df74b1059ba98f7d5d657b
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57815163"
---
# <a name="c-compile-without-linking"></a>/c (Kompilieren ohne Verknüpfen)

Verhindert den automatischen Aufruf von links an.

## <a name="syntax"></a>Syntax

```
/c
```

## <a name="remarks"></a>Hinweise

Beim Kompilieren mit **/c** nur OBJ-Dateien erstellt. Sie müssen Links mit den entsprechenden Dateien und Optionen zum Ausführen der Verknüpfungsphase des Builds explizit aufrufen.

Alle internen Projekt erstellt haben, in der Entwicklungsumgebung verwendet der **/c** standardmäßig die Option.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

- Diese Option ist nicht in der Entwicklungsumgebung verfügbar.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Wie Sie diese Compileroption programmgesteuert festlegen, erfahren Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileOnly%2A>.

## <a name="example"></a>Beispiel

Die folgende Befehlszeile erstellt, die Objektdateien FIRST.obj und Second.obj erstellt wird. Die Datei THIRD.obj wird ignoriert.

```
CL /c FIRST.C SECOND.C THIRD.OBJ
```

Um eine ausführbare Datei zu erstellen, müssen Sie den LINK aufrufen:

```
LINK firsti.obj second.obj third.obj /OUT:filename.exe
```

## <a name="see-also"></a>Siehe auch

[MSVC-Compiler-Optionen](compiler-options.md)<br/>
[MSVC-Compiler-Befehlszeilensyntax](compiler-command-line-syntax.md)
