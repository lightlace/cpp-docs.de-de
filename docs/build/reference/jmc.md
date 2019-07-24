---
title: /JMC (Debuggen von „Nur eigenen Code“)
ms.date: 08/20/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.SupportJustMyCode
helpviewer_keywords:
- /JMC compiler option [C++]
- Just my code [C++]
- -JMC compiler option [C++]
- User code, debugging
- JMC compiler option [C++]
ms.openlocfilehash: 90fcad40b3322f8a8ae7ffc58875c2850f143138
ms.sourcegitcommit: 0867d648e0955ebad7260b5fbebfd6cd4d58f3c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/19/2019
ms.locfileid: "68341011"
---
# <a name="jmc-just-my-code-debugging"></a>/JMC (Debuggen von „Nur eigenen Code“)

Gibt die Compilerunterstützung für System eigenes *nur eigenen Code* Debuggen im Visual Studio-Debugger an. Diese Option unterstützt die Benutzereinstellungen, mit denen Visual Studio System-, Framework-, Bibliotheks-und andere Nichtbenutzer Aufrufe überspringen und diese Aufrufe im Aufruf Stapelfenster reduzieren kann. Die **/JMC** -Compileroption ist ab Visual Studio 2017, Version 15,8, verfügbar.

## <a name="syntax"></a>Syntax

> **/JMC**\[ **-** ]

## <a name="remarks"></a>Hinweise

Die Visual Studio- [nur eigenen Code](/visualstudio/debugger/just-my-code) Einstellungen geben an, ob der Visual Studio-Debugger System-, Framework-, Bibliotheks-und andere Nichtbenutzer Aufrufe überschreitet. Die **/JMC** -Compileroption aktiviert die Unterstützung für das C++ nur eigenen Code Debuggen in ihrem nativen Wenn **/JMC** aktiviert ist, fügt der Compiler Aufrufe an eine Hilfsfunktion `__CheckForDebuggerJustMyCode`,, in den Prolog der Funktion ein. Die Hilfsfunktion bietet Hooks, die Visual Studio-Debugger-nur eigenen Code Schritt Vorgänge unterstützen. Wenn Sie nur eigenen Code im Visual Studio-Debugger aktivieren möchten **, wählen Sie** > in der Menüleiste Extras**Optionen**aus, und legen Sie dann die Option in**Allgemeine** >  **Debuggen** > **aktivieren nur eigenen Code**fest.

Die **/JMC** -Option erfordert, dass Ihr Code mit der C-Lauf Zeit Bibliothek (CRT) verknüpft `__CheckForDebuggerJustMyCode` ist, die die-Hilfsfunktion bereitstellt. Wenn Ihr Projekt nicht mit der CRT verknüpft wird, wird möglicherweise Linker Error **LNK2019: nicht aufgelöstes externes Symbol __CheckForDebuggerJustMyCode**angezeigt. Um diesen Fehler zu beheben, verknüpfen Sie entweder mit der CRT, oder deaktivieren Sie die Option **/JMC** .

Standardmäßig ist die **/JMC** -Compileroption deaktiviert. Ab Visual Studio 2017 Version 15,8 ist diese Option jedoch in den meisten Visual Studio-Projektvorlagen aktiviert. Um diese Option explizit zu deaktivieren, verwenden Sie die **/JMC-** -Option in der Befehlszeile. Öffnen Sie in Visual Studio das Dialogfeld Eigenschaften Seiten des Projekts, und ändern Sie die Eigenschaft **Unterstützung nur eigenen Code Debuggen** auf der Eigenschaften Seite Eigenschaften von **Konfigurations Eigenschaften** >  > **C/C++** **Allgemein** in **Nein**.

Weitere Informationen [ C++ ](/visualstudio/debugger/just-my-code#BKMK_C___Just_My_Code) finden Sie unter nur eigenen Code in [angeben, ob nur Benutzer Code mithilfe nur eigenen Code in Visual Studio debuggt](/visualstudio/debugger/just-my-code)werden soll C++ , und im Blog Beitrag des visuellen Teams, der nur eigenen Code Schritt-für- [Schritt-in Visual Studio angekündigt C++ ](https://blogs.msdn.microsoft.com/vcblog/2018/06/29/announcing-jmc-stepping-in-visual-studio/)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Wählen Sie die **Eigenschaften Seite Konfigurations Eigenschaften** > **C++C/**  > allgemein aus.

1. Ändern Sie die Eigenschaft **Unterstützung nur eigenen Code Debuggen** .

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)<br/>
