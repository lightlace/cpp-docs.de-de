---
title: '/ Zc: wchar_t (Wchar_t ist der systemeigene Typ) | Microsoft Docs'
ms.custom: ''
ms.date: 03/01/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.TreatWChar_tAsBuiltInType
- VC.Project.VCCLCompilerTool.TreatWChar_tAsBuiltInType
- /Zc:wchar_t
dev_langs:
- C++
helpviewer_keywords:
- /Zc compiler options [C++]
- -Zc compiler options [C++]
- wchar_t type
- Conformance compiler options
- Zc compiler options [C++]
ms.assetid: b0de5a84-da72-4e5a-9a4e-541099f939e0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 061aa4a70412a0b51450470e690bea5633b764ad
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32381280"
---
# <a name="zcwchart-wchart-is-native-type"></a>/Zc:wchar_t (wchar_t ist der systemeigene Typ)

Analysieren Sie `wchar_t` als integrierten Typ entsprechend dem C++-Standard.

## <a name="syntax"></a>Syntax

> **/Zc:wchar_t**[**-**]

## <a name="remarks"></a>Hinweise

Wenn **/Zc: wchar_t** aktiviert ist, `wchar_t` ist ein Schlüsselwort für einen integrierten-Ganzzahltyp im als C++ kompilierten Code. Wenn **/Zc:wchar_t-** (mit einem Minuszeichen) wird angegeben, oder im Code als C kompiliert, `wchar_t` ist kein integrierter Typ. Stattdessen `wchar_t` ist definiert als eine `typedef` für `unsigned short` in der stddef.h kanonische Header. (Die Microsoft-Implementierung definiert in einem anderen Header, der vom stddef.h eingeschlossen wird und andere standard-Header.)

Wir empfehlen nicht **/Zc:wchar_t-** , da die C++-Standard, die erfordert `wchar_t` ein integrierter Typ sein. Die Verwendung der `typedef`-Version kann Portabilitätsprobleme verursachen. Wenn Sie ein von früheren Versionen von Visual C++ Upgrade und Compilerfehler auftreten, [C2664](../../error-messages/compiler-errors-2/compiler-error-c2664.md) , da der Code versucht, eine implizite Konvertierung einer `wchar_t` auf `unsigned short`, es wird empfohlen, dass Sie den Code, um den Fehler zu beheben, stattdessen ändern Einstellung **/Zc:wchar_t-**.

Die **/Zc: wchar_t** Option ist standardmäßig in C++-Kompilierungen und in C# Kompilierungen ignoriert. Die [/ liberalen-](permissive-standards-conformance.md) Option wirkt sich nicht **/Zc: wchar_t**.

Microsoft implementiert `wchar_t` als 2-Byte-Wert ohne Vorzeichen. Sie ordnet die Microsoft-spezifischen systemeigenen Typ `__wchar_t`. Weitere Informationen zu `wchar_t`, finden Sie unter [Datentypbereiche](../../cpp/data-type-ranges.md) und [grundlegende Typen](../../cpp/fundamental-types-cpp.md).

Wenn Sie neuen Code schreiben, der mit älterem Code zusammenwirken, die noch verwendet die `typedef` Version `wchar_t`, können Sie für beide Überladungen Bereitstellen der `unsigned short` und `__wchar_t` Variationen des `wchar_t`, sodass der Code mit der verknüpft werden kann mit Code kompiliert **/Zc: wchar_t** oder Code kompiliert, ohne ihn. Andernfalls müssen Sie bieten zwei verschiedene builds der Bibliothek, eine mit und ohne **/Zc: wchar_t** aktiviert. Allerdings wird in beiden Fällen empfohlen, den älteren und den neuen Code mit demselben Compiler zu erstellen. Kombinieren Sie niemals die Binärdateien, die mit unterschiedlichen Compilern erstellt wurden.

Wenn **/Zc: wchar_t** angegeben wird,  **\_WCHAR\_T\_definierte** und  **\_NATIVE\_WCHAR\_T\_definierte** Symbole definiert sind. Weitere Informationen finden Sie unter [Predefined Macros](../../preprocessor/predefined-macros.md).

Wenn Ihr Code die globalen Compiler-COM-Funktionen verwendet, da **/Zc: wchar_t** ist jetzt auf standardmäßig, es wird empfohlen, dass Sie explizite Verweise auf comsupp.lib ändern (entweder über die [comment-Pragma](../../preprocessor/comment-c-cpp.md) oder auf der Befehlszeile) auf "comsuppw.lib" oder "comsuppwd.lib". (Muss beim Kompilieren mit **/Zc:wchar_t-**, verwenden Sie "comsupp.lib".) Wenn Sie die comdef.h-Headerdatei einfügen, wird die richtige Bibliothek für Sie angegeben. Weitere Informationen zur Compiler-COM-Unterstützung finden Sie unter [Compiler COM unterstützt](../../cpp/compiler-com-support.md).

Die `wchar_t` integrierter Typ wird nicht unterstützt, wenn Sie C#-Code kompilieren. Weitere Informationen über Konformitätsprobleme in Visual C++ finden Sie unter [nicht standardmäßigem Verhalten](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Sprache** Seite.

1. Ändern der **Wchar_t als integrierten Typ behandeln** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.TreatWChar_tAsBuiltInType%2A>.

## <a name="see-also"></a>Siehe auch

[/Zc (Übereinstimmung)](../../build/reference/zc-conformance.md)<br/>
