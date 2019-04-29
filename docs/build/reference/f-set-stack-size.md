---
title: /F (Stapelgröße festlegen)
ms.date: 11/04/2016
f1_keywords:
- /f
helpviewer_keywords:
- set stack size compiler option
- F compiler option [C++]
- -F compiler option [C++]
- /F compiler option [C++]
- stack, setting size
ms.assetid: 17320b6f-8305-445b-9ec2-75833f4b29e0
ms.openlocfilehash: 9db595daa7de7820b594a8515ece7481b4382c98
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62293094"
---
# <a name="f-set-stack-size"></a>/F (Stapelgröße festlegen)

Legt die Stapelgröße der Anwendung in Bytes fest.

## <a name="syntax"></a>Syntax

> **/ F** *Anzahl*

## <a name="arguments"></a>Argumente

*Anzahl*<br/>
Die Stapelgröße in Bytes.

## <a name="remarks"></a>Hinweise

Ohne diese Option wird standardmäßig die Größe des Stapels zu 1 MB. Die *Anzahl* Argument kann sein, in Dezimalstellen oder C-Notation. Das Argument kann zwischen 1 und die maximale Stapelgröße, die vom Linker akzeptiert. Der Linker rundet den angegebenen Wert in die nächsten 4 Bytes ab. Der Abstand zwischen **/f** und *Anzahl* ist optional.

Sie müssen möglicherweise die Größe des Stapels zu erhöhen, wenn das Programm auf Stack Overflow-Nachrichten abruft.

Sie können auch die Stapelgröße festlegen, durch:

- Mithilfe der **/STACK** -Linkeroption. Weitere Informationen finden Sie unter [/STACK](stack.md).

- Verwenden von EDITBIN für die .exe-Datei. Weitere Informationen finden Sie unter [EDITBIN-Referenz](editbin-reference.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
