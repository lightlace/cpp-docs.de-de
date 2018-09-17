---
title: -F (Stapelgröße festlegen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /f
dev_langs:
- C++
helpviewer_keywords:
- set stack size compiler option
- F compiler option [C++]
- -F compiler option [C++]
- /F compiler option [C++]
- stack, setting size
ms.assetid: 17320b6f-8305-445b-9ec2-75833f4b29e0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 244fea4b776f0713b6fb2281563e39d27a910a2d
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45704245"
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