---
title: /Wp64 (Nach 64-Bit-Portabilitätsproblemen suchen)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.Detect64BitPortabilityProblems
- VC.Project.VCCLCompilerTool.Detect64BitPortabilityProblems
- /wp64
helpviewer_keywords:
- 64-bit compiler [C++], detecting portability problems
- /Wp64 compiler option [C++]
- -Wp64 compiler option [C++]
- Wp64 compiler option [C++]
ms.assetid: 331ae5aa-e627-4d03-8f63-dd2c2d76dadd
ms.openlocfilehash: 5a3cdaf85fa4dc05ece54fc630cb69fc93650e6b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62316547"
---
# <a name="wp64-detect-64-bit-portability-issues"></a>/Wp64 (Nach 64-Bit-Portabilitätsproblemen suchen)

Diese Compileroption ist veraltet. In Versionen von Visual Studio vor Visual Studio 2013 werden dadurch 64-Bit-Portabilitätsprobleme für Typen ermittelt, die mit dem Schlüsselwort [__w64](../../cpp/w64.md) markiert sind.

## <a name="syntax"></a>Syntax

```
/Wp64
```

## <a name="remarks"></a>Hinweise

In Versionen von Visual Studio vor Visual Studio 2013, standardmäßig die **/Wp64** Compileroption ist deaktiviert, in der MSVC-Compiler, die 32-Bit-X86 erstellt Code, und auf in der MSVC-Compiler, die 64-Bit X64 erstellt Code.

> [!IMPORTANT]
>  Die [/Wp64](wp64-detect-64-bit-portability-issues.md) Compileroption und das [__w64](../../cpp/w64.md) -Schlüsselwort sind in Visual Studio 2010 und Visual Studio 2012 veraltet und werden ab Visual Studio 2013 nicht mehr unterstützt. Wenn Sie ein Projekt konvertieren, das diesen Schalter verwendet, wird der Schalter während der Konvertierung nicht migriert. Um diese Option in Visual Studio 2010 oder Visual Studio 2012 zu verwenden, müssen Sie den Compilerschalter unter **Zusätzliche Optionen** im **Befehlszeilenabschnitt** der Projekteigenschaften eingeben. Wenn Sie die **/Wp64** -Compileroption in der Befehlszeile verwenden, gibt der Compiler eine Befehlszeilenwarnung D9002 aus. Verwenden Sie statt dieser Option und dieses Schlüsselworts zum Ermitteln von 64-Bit-Portabilitätsproblemen einen MSVC-Compiler, der eine 64-Bit-Plattform konzipiert ist, und geben die [/W4](compiler-option-warning-level.md) Option. Weitere Informationen finden Sie unter [Konfigurieren von C++-Projekte für 64-Bit, X64 Ziele](../configuring-programs-for-64-bit-visual-cpp.md).

Variablen der folgenden Typen werden auf einem 32-Bit-Betriebssystem getestet, als ob sie auf einem 64-Bit-Betriebssystem verwendet würden:

- int

- long

- pointer

Wenn Sie Ihre Anwendung regelmäßig mit einem Compiler, der 64-Bit X64 erstellt kompilieren Code können Sie nur deaktivieren, **/Wp64** in den 32-Bit-Kompilierungen, da der 64-Bit-Compiler alle Probleme erkennt. Weitere Informationen zum abzielen auf ein Windows-64-Bit-Betriebssystem, finden Sie unter [Konfigurieren von C++-Projekte für 64-Bit, X64 Ziele](../configuring-programs-for-64-bit-visual-cpp.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.

   Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .

1. Ändern Sie das Feld **Zusätzliche Optionen** so, dass **/Wp64**eingeschlossen ist.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Detect64BitPortabilityProblems%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)<br/>
[Konfigurieren von C++-Projekten für 64-Bit-X64 Ziele](../configuring-programs-for-64-bit-visual-cpp.md)
