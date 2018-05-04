---
title: -std (Language-Standardversion angeben) | Microsoft Docs
ms.custom: ''
ms.date: 11/16/2017
ms.topic: reference
f1_keywords:
- /std
- -std
- VC.Project.VCCLCompilerTool.CppLanguageStandard
dev_langs:
- C++
ms.assetid: 0acb74ba-1aa8-4c05-b96c-682988dc19bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7fed80f0f9763b7e988c40a9d9f38f4e0f18eeb1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="std-specify-language-standard-version"></a>/Std (Language-Standardversion angeben)

Enable unterstützt C++-Sprachfeatures aus der angegebenen Version der Programmiersprache C++ standard.

## <a name="syntax"></a>Syntax

> /Std: [C ++ 14 | C ++ 17 | C ++ neueste]

## <a name="remarks"></a>Hinweise

Die **/std** Option verwendet, um die versionsspezifischen ISO C++ programming Language-standard-Funktionen aktiviert, während der Kompilierung des Codes zu steuern. Diese Option können Sie Unterstützung für bestimmte neue Sprache und Library-Funktionen zu deaktivieren, die einen Umbruch kann vorhandenen Code, der eine bestimmte Version der Sprache entspricht standard. Standardmäßig **/std:c ++ 14** angegeben wird, wodurch deaktiviert, Sprache und Standardbibliotheksfunktionen gefunden in höheren Versionen der Programmiersprache C++-standard. Verwendung **/std:c ++ 17** C ++ 17-Standard-spezifische Funktionen und das Verhalten zu aktivieren. Verwenden Sie zum expliziten Aktivieren von der neuesten unterstützten Compiler und Standardbibliotheksfunktionen **/std:c ++ neueste**.

Die Standardeinstellung **/std:c ++ 14** Option ermöglicht es, den Satz von C ++ 14-Funktionen von Visual C++-Compiler implementiert. Diese Option deaktiviert, Compiler und die Standardbibliothek-Unterstützung für Funktionen, die geändert werden oder neu in neueren Versionen der Sprache, standard, mit Ausnahme von einigen C ++ 17-Funktionen bereits in früheren Versionen von Visual C++-Compiler implementiert. Um zu vermeiden, wichtige Änderungen für Benutzer, die bereits Abhängigkeiten auf den Funktionen ab Visual Studio 2015 Update 2 ausgeführt haben, diese Funktionen bleiben aktiviert, wenn die **/std:c ++ 14** angegeben wird:

- [Regeln für Auto "mit" braced-Init-lists](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3922.html)

- [TypeName in Vorlagen-Vorlagenparameter](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4051.html)

- [Entfernen von Trigraphen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4086.html)

- [Attribute für Namespaces und Enumeratoren](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4266.html)

- [U8-Zeichenliterale](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4267.html)

Zusätzliche Informationen für die C ++ 14 und C ++ 17-Funktionen aktiviert sind, wenn **/std:c ++ 14** ist angegeben, siehe die Hinweise im [Konformität von Visual C++ Language](../../visual-cpp-language-conformance.md).
  
Die **/std:c ++ 17** Option ermöglicht den vollständigen Satz von C ++ 17-Funktionen von Visual C++-Compiler implementiert. Diese Option deaktiviert die Unterstützung von Compiler- und Standardbibliotheken für Features, die in Versionen des Arbeitsentwurfs und Fehlerbehebungsaktualisierungen des C++-Standards nach C++17 neu sind oder geändert wurden.  
  
Die **/std:c ++ neueste** Option ermöglicht es den Satz von C++-Sprache und Bibliothek-Features von Visual C++ die meisten verfolgen implementiert neueste C ++ 20 Arbeitsentwurf und austragen Updates des C++-Standards, die nicht in C ++ 17 enthalten sind. Verwenden Sie diese Option zum Abrufen der Post-von C ++ 17-Sprachfunktionen, die durch den Compiler und die Standardbibliothek unterstützt. Eine Liste der unterstützten Sprachen und Bibliotheksfunktionen, finden Sie unter [Neues bei Visual C++](../../what-s-new-for-visual-cpp-in-visual-studio.md). Die **/std:c ++ neueste** Option ermöglicht keine Funktionen, die geschützt werden, indem Sie die **/ experimentelle** wechseln.  
  
Die **/std** faktisch während einer C++-Kompilierung die Option kann mithilfe der erkannt werden die [ \_MSVC\_LANG](../../preprocessor/predefined-macros.md) Präprozessormakro. Weitere Informationen finden Sie unter [Präprozessor Makros](../../preprocessor/predefined-macros.md).

Die **/std:c ++ 14** und **/std:c ++ neueste** Optionen sind ab Visual C++ 2015 Update 3. Die **/std:c ++ 17** Option ist in Visual C++ 2017 Version 15.3 ab. Wie bereits erwähnt, einige C ++ 17-standard wird das Verhalten aktiviert, indem die **/std:c ++ 14** Option jedoch alle anderen C ++ 17-Funktionen aktiviert, indem **/std:c ++ 17**.
  
> [!NOTE]
> Je nach den Visual C++-Compiler Version oder ein Update, bestimmte C ++ 14-C ++ 17-Funktionen möglicherweise nicht vollständig implementiert oder vollständig-konforme Funktion bei der Angabe der **/std:c ++ 14** oder **/std:c ++ 17** Optionen. Angenommen, der Visual C++ 2017 RTM-Compiler unterstützt nicht vollständig C ++ 14-konformen `constexpr`, Ausdruck SFINAE oder 2-Phasen-Namenssuche. Einen Überblick über die Konformität Sprache C++ in Visual C++ durch Releaseversion finden Sie unter [Konformität von Visual C++ Language](../../visual-cpp-language-conformance.md). 
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie **Konfigurationseigenschaften**, **C/C++-**, **Sprache**.  
  
3.  In **C++ Language Standard**, wählen Sie die sprachenstandard-, um aus der Dropdown-Steuerelement unterstützen, und wählen Sie dann **OK** oder **übernehmen** zum Speichern der Änderungen.  
  
## <a name="see-also"></a>Siehe auch  
  
[Compileroptionen](../../build/reference/compiler-options.md)   
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
