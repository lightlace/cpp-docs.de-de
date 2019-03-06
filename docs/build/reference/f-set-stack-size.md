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
ms.openlocfilehash: 31d694c176afd3c79cde172248bfcd93d1346b54
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57414446"
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

- Mithilfe der **/STACK** -Linkeroption. Weitere Informationen finden Sie unter [/STACK](../../build/reference/stack.md).

- Verwenden von EDITBIN für die .exe-Datei. Weitere Informationen finden Sie unter [EDITBIN-Referenz](../../build/reference/editbin-reference.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
