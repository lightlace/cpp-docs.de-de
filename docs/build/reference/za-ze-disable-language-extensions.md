---
title: -Za, - Ze (Spracherweiterungen deaktivieren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.DisableLanguageExtensions
- /za
- /ze
- VC.Project.VCCLCompilerTool.DisableLanguageExtensions
dev_langs:
- C++
helpviewer_keywords:
- -Za compiler option [C++]
- Za compiler option [C++]
- language extensions, disabling in compiler
- -Ze compiler option [C++]
- language extensions
- enable language extensions
- /Za compiler option [C++]
- /Ze compiler option [C++]
- Disable Language Extensions compiler option
- Ze compiler option [C++]
ms.assetid: 65e49258-7161-4289-a176-7c5c0656b1a2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7e30fb37be6738b7100b84a1898c02ab4230c41b
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42597572"
---
# <a name="za-ze-disable-language-extensions"></a>/Za, /Ze (Spracherweiterungen deaktivieren)
Die **/Za** Compileroption gibt einen Fehler für Sprachkonstrukte, die nicht mit ANSI-C89 oder ISO C ++ 11 kompatibel sind. Die **/Ze** -Compileroption verwenden, die standardmäßig aktiviert ist, ermöglicht Microsoft-Erweiterungen.  
  
## <a name="syntax"></a>Syntax  
  
```  
/Za  
/Ze  
```  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Die **/Ze** Option ist veraltet, da das Verhalten standardmäßig aktiviert ist. Es wird empfohlen, die [/Zc (Übereinstimmung)](../../build/reference/zc-conformance.md) Compileroptionen sprachspezifischen Erweiterungsfunktionen steuern. Eine Liste der Ersetzte Compileroptionen, finden Sie unter den **veraltete und entfernte Compileroptionen** im Abschnitt [Compiler Options Listed by Category](../../build/reference/compiler-options-listed-by-category.md).  
  
 Visual C++-Compiler bietet eine Reihe von Funktionen über die angegebenen in das ANSI-C89, ISO C99 oder ISO C++-Standards. Diese Funktionen werden zusammenfassend als Microsoft-Erweiterungen für C und C++ bezeichnet. Diese Erweiterungen sind standardmäßig verfügbar und nicht verfügbar, wenn die **/Za** angegeben wird. Weitere Informationen zu spezifischen Erweiterungen finden Sie unter [Microsoft Extensions für C und C++](../../build/reference/microsoft-extensions-to-c-and-cpp.md).  
  
 Es wird empfohlen, dass Sie spracherweiterungen werden, indem deaktiviert die **/Za** option, wenn Sie Ihr Programm in andere Umgebungen zu portieren möchten. Bei der **/Za** angegeben ist, behandelt der Compiler-Schlüsselwörter als einfache Bezeichner erweiterte Microsoft, die anderen Microsoft-Erweiterungen deaktiviert und definiert automatisch die `__STDC__` vordefiniertes Makro für die C-Programmen.  
  
 Andere Compileroptionen verwendet mit **/Za** kann beeinflussen, wie der Compiler stellt sicher, Einhaltung von Standards. Z. B. **/Za** und [/fp (Festlegen des Gleitkommaverhaltens)](../../build/reference/fp-specify-floating-point-behavior.md) kann vom Typ Gleitkommazahl heraufstufung zu Verhalten führen, die nicht entspricht, die ISO C99 oder C ++ 11-Standards.  
  
 Möglichkeiten zum Angeben von Einstellungen für das bestimmte standardkonforme Verhalten, finden Sie unter den [/Zc](../../build/reference/zc-conformance.md) -Compileroption.  
  
 Weitere Informationen über Konformitätsprobleme mit Visual C++ finden Sie unter [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie im Navigationsbereich **Konfigurationseigenschaften**, **C/C++-**, **Sprache**.  
  
3.  Ändern der **Spracherweiterungen deaktivieren** Eigenschaft.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DisableLanguageExtensions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [/Zc (Übereinstimmung)](../../build/reference/zc-conformance.md)