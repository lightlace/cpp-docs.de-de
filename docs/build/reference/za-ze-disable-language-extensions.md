---
title: -Za, - Ze (Spracherweiterungen deaktivieren) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6866ccaac789ab2cd5af4703d7f81e30f554db84
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="za-ze-disable-language-extensions"></a>/Za, /Ze (Spracherweiterungen deaktivieren)
Die **"/ Za"** (Compileroption) gibt einen Fehler für Sprachkonstrukte, die nicht mit C89 ANSI oder ISO C ++ 11 kompatibel sind. Die **"/ Ze"** (Compileroption), die standardmäßig aktiviert ist, aktiviert Microsoft-Erweiterungen.  
  
## <a name="syntax"></a>Syntax  
  
```  
/Za  
/Ze  
```  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Die **"/ Ze"** Option ist veraltet, da ihr Verhalten standardmäßig aktiviert ist. Es wird empfohlen, die [/Zc (Übereinstimmung)](../../build/reference/zc-conformance.md) Compileroptionen Erweiterungsfunktionen sprachspezifischen steuern. Eine Liste der veralteten Compileroptionen, finden Sie unter der **veraltete und entfernte Compileroptionen** im Abschnitt [Compileroptionen nach Kategorien sortiert](../../build/reference/compiler-options-listed-by-category.md).  
  
 Die [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] Compiler bietet eine Reihe von Features hinausgehen ANSI C89, ISO C99 oder ISO C++-Standards. Diese Funktionen werden zusammenfassend als Microsoft-Erweiterungen für C und C++ bezeichnet. Diese Erweiterungen werden standardmäßig verfügbar und nicht verfügbar, wenn die **"/ Za"** angegeben wird. Weitere Informationen zu spezifischen Erweiterungen finden Sie unter [Microsoft Extensions für C und C++](../../build/reference/microsoft-extensions-to-c-and-cpp.md).  
  
 Es wird empfohlen, dass Sie spracherweiterungen werden, indem deaktiviert die **"/ Za"** option, wenn Sie beabsichtigen, die port-Programms in anderen Umgebungen. Wenn **"/ Za"** angegeben ist, wird der Compiler behandelt Schlüsselwörter als einfache Bezeichner erweiterte Microsoft- und deaktiviert die anderen Microsoft-Erweiterungen automatisch definiert die `__STDC__` vordefiniertes Makro für C-Programme.  
  
 Andere Compileroptionen verwendet mit **"/ Za"** kann beeinflussen, wie der Compiler die Einhaltung von Standards sicherstellt. Beispielsweise **"/ Za"** und [/fp (Festlegen von Floating-Verhalten)](../../build/reference/fp-specify-floating-point-behavior.md) möglicherweise Gleitkommatyp Promotion-Verhalten, das nicht entspricht dem ISO C99 oder C ++ 11-Standards.  
  
 Möglichkeiten zum Angeben von bestimmten standardkonforme verhaltenseinstellungen, finden Sie unter der [/Zc](../../build/reference/zc-conformance.md) -Compileroption.  
  
 Weitere Informationen über Konformitätsprobleme mit [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)], finden Sie unter [nicht standardmäßigem Verhalten](../../cpp/nonstandard-behavior.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie im Navigationsbereich **Konfigurationseigenschaften**, **C/C++-**, **Sprache**.  
  
3.  Ändern der **Spracherweiterungen deaktivieren** Eigenschaft.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DisableLanguageExtensions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [/ Zc (Übereinstimmung)](../../build/reference/zc-conformance.md)