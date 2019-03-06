---
title: / JMC (nur mein Code Debuggen)
ms.date: 08/20/2018
f1_keywords:
- /JMC
helpviewer_keywords:
- /JMC compiler option [C++]
- Just my code [C++]
- -JMC compiler option [C++]
- User code, debugging
- JMC compiler option [C++]
ms.openlocfilehash: d1950ff4a973ddbd23ff902ba4afb0d45dacb0e5
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57417761"
---
# <a name="jmc-just-my-code-debugging"></a>/ JMC (nur mein Code Debuggen)

Gibt der Compiler-Unterstützung für Native *nur mein Code* Debuggen in Visual Studio-Debugger. Diese Option unterstützt die benutzereinstellungen, mit denen Visual Studio, System, Framework, Bibliothek und andere Aufrufe überspringen und diese Aufrufe in das Aufruflistenfenster zu reduzieren. Die **/JMC** Compileroption ist in Visual Studio 2017 Version 15.8 ab.

## <a name="syntax"></a>Syntax

> **/JMC**\[**-**]

## <a name="remarks"></a>Hinweise

Visual Studio [nur mein Code](/visualstudio/debugger/just-my-code) Einstellungen angeben, ob es sich bei Visual Studio-Debugger über System, Framework, Bibliothek und andere Aufrufe Schritte. Die **/JMC** Compileroption aktiviert die Unterstützung für nur mein Code in Ihrem nativen C++-Code zu debuggen. Wenn **/JMC** ist aktiviert, fügt der Compiler Aufrufe an eine Hilfsmethode, `__CheckForDebuggerJustMyCode`, im Prolog Funktion. Die Hilfsfunktion bietet Hooks, die Visual Studio-Debugger nur mein Code-Schritt-Vorgänge zu unterstützen. So aktivieren Sie nur mein Code in Visual Studio-Debugger, auf der Menüleiste wählen **Tools** > **Optionen**, und legen Sie dann die Option in **Debuggen**  >  **Allgemeine** > **nur meinen Code aktivieren**.

Die **/JMC** Option erfordert, dass Ihr Code auf die C-Laufzeitbibliothek (CRT), verknüpft die bietet die `__CheckForDebuggerJustMyCode` Hilfsfunktion. Wenn Ihr Projekt nicht mit der CRT verknüpft ist, wird möglicherweise angezeigt Linkerfehler **LNK2019: nicht aufgelöste externe Symbol __CheckForDebuggerJustMyCode**. Um diesen Fehler zu beheben, entweder mit der CRT verknüpft, oder Deaktivieren der **/JMC** Option.

In der Standardeinstellung die **/JMC** Compileroption ist deaktiviert. Ab Visual Studio 2017 Version 15.8 diese Option ist jedoch in den meisten Visual Studio-Projektvorlagen aktiviert. Um diese Option explizit zu deaktivieren, verwenden die **/JMC-** Option in der Befehlszeile. In Visual Studio, öffnen Sie das Dialogfeld Eigenschaftenseiten für Projekt, und ändern Sie die **Unterstützung nur mein Codedebuggen** -Eigenschaft in der **Konfigurationseigenschaften** > **C-/C++-**  >  **Allgemeine** Eigenschaftenseite **keine**.

Weitere Informationen finden Sie unter [C++ nur mein Code](/visualstudio/debugger/just-my-code#BKMK_C___Just_My_Code) in [geben an, ob nur Benutzercode, die mit nur mein Code in Visual Studio Debuggen](/visualstudio/debugger/just-my-code), und die Visual C++-Team-Blog-Post [Ankündigung C++ nur mein Code In Visual Studio schrittweise](https://blogs.msdn.microsoft.com/vcblog/2018/06/29/announcing-jmc-stepping-in-visual-studio/).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **allgemeine** Eigenschaftenseite.

1. Ändern der **Unterstützung nur mein Codedebuggen** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)<br/>
