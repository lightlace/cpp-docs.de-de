---
title: /errorReport (Meldung über interne Compilerfehler)
description: Referenz für die BefehlszeilenoptionC++ "Microsoft C/Compiler/errorreport".
ms.date: 02/09/2020
f1_keywords:
- VC.Project.VCCLCompilerTool.ErrorReporting
- /errorreport
helpviewer_keywords:
- /errorReport compiler option [C++]
- -errorReport compiler option [C++]
ms.assetid: 819828f8-b0a5-412c-9c57-bf822f17e667
ms.openlocfilehash: 8d4a3c4d5fd918973bbf8057e0c073c680e6995e
ms.sourcegitcommit: 8414cd91297dea88c480e208c7b5301db9972f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77257649"
---
# <a name="errorreport-report-internal-compiler-errors"></a>/errorReport (Meldung über interne Compilerfehler)

> [!NOTE]
> Die **/errorreport** -Option ist veraltet. Ab Windows Vista wird die Fehlerberichterstattung durch [Windows-Fehlerberichterstattung (wer)](/windows/win32/wer/windows-error-reporting) -Einstellungen gesteuert.

## <a name="syntax"></a>Syntax

> **/errorreport:** \[**keine** \| **Eingabeaufforderung** \| **warte \| Schlange** **senden** ]

## <a name="remarks"></a>Bemerkungen

Ein interner Compilerfehler (ICE), wenn der Compiler eine Quell Code Datei nicht verarbeiten kann. Wenn ein Ice auftritt, erzeugt der Compiler keine Ausgabedatei oder eine sinnvolle Diagnose, die Sie verwenden können, um den Code zu korrigieren.

Die **/errorreport** -Argumente werden von den Windows-Fehlerberichterstattung Dienst Einstellungen überschrieben. Der Compiler sendet automatisch Berichte interner Fehler an Microsoft, wenn die Berichterstellung durch Windows-Fehlerberichterstattung aktiviert wird. Wenn Windows-Fehlerberichterstattung deaktiviert ist, wird kein Bericht gesendet.


### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Öffnen Sie die **Eigenschaften Seite Konfigurations Eigenschaften** > **C++ C/**  > **erweitert** .

1. Ändern Sie die Eigenschaft **Fehlerberichterstattung** .

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ErrorReporting%2A>.

## <a name="see-also"></a>Weitere Informationen

[MSVC-Compileroptionen](compiler-options.md)\
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
