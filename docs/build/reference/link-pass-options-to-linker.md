---
title: /link (Optionen an Linker übergeben)
ms.date: 03/25/2019
f1_keywords:
- /link
helpviewer_keywords:
- /link compiler option [C++]
- pass options to linker
- link compiler option [C++]
- linker [C++], passing options to
- -link compiler option [C++]
- cl.exe compiler [C++], passing options to linker
ms.assetid: 16902a94-c094-4328-841f-3ac94ca04848
ms.openlocfilehash: 37743e855c933b6236b5e7a837db257f332a3037
ms.sourcegitcommit: bbaf65f8ed1af12828b38f8eacd24f934ac0e538
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2019
ms.locfileid: "67155782"
---
# <a name="link-pass-options-to-linker"></a>/link (Optionen an Linker übergeben)

Übergibt ein oder mehrere Optionen des Linkers an den Linker an.

## <a name="syntax"></a>Syntax

> **/link** *linker-options*

## <a name="arguments"></a>Argumente

*linker-options*<br/>
Die Linkeroption oder die Optionen an Linker übergeben werden.

## <a name="remarks"></a>Hinweise

Die **/link** Option und die Optionen des Linkers müssen nach jedem Dateinamen und CL-Optionen angezeigt werden. Ein Leerzeichen ist erforderlich, zwischen **/link** und alle Optionen des Linkers. Weitere Informationen finden Sie unter [MSVC Linker Verweis](linking.md).

## <a name="example"></a>Beispiel

Diese Beispiel-Befehlszeile kompiliert *hello.cpp* und verknüpft es mit der vorhandenen Objektdatei *there.obj*. Anschließend übergibt es ein zusätzliches **/Version** Befehl an den Linker:

`cl /W4 /EHsc hello.cpp there.obj /link /VERSION:3.14`

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

Die IDE sendet normalerweise separate Befehle zum Kompilieren und verknüpfen Sie Ihren Code. Sie können die Optionen des Linkers in Ihrem Projekt-Eigenschaftenseiten festlegen.

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **Linker** Ordner.

1. Ändern Sie eine oder mehrere Eigenschaften an. Klicken Sie auf **OK**, um die Änderungen zu speichern.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Diese Compileroption kann nicht programmgesteuert geändert werden.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
