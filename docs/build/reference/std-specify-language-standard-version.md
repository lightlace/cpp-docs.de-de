---
title: /std (Standardversion für die Sprache festlegen)
ms.date: 05/16/2019
f1_keywords:
- /std
- -std
- VC.Project.VCCLCompilerTool.CppLanguageStandard
ms.assetid: 0acb74ba-1aa8-4c05-b96c-682988dc19bd
ms.openlocfilehash: 9bdeb92e03b3ae00258ac48a29cec42ef7e18e81
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68241216"
---
# <a name="std-specify-language-standard-version"></a>/std (Standardversion für die Sprache festlegen)

Aktivieren Sie unterstützte Features der Programmiersprache C++ aus der angegebenen Version des C++-Sprachstandards.

## <a name="syntax"></a>Syntax

> /std:\[c++14\|c++17\|c++latest]

## <a name="remarks"></a>Hinweise

Die Option **/std** ist in Visual Studio 2017 und höher verfügbar. Sie wird zum Steuern der versionsspezifischen Features gemäß dem ISO C++-Programmiersprachenstandard verwendet, die während der Kompilierung Ihres Codes aktiviert sind. Diese Option ermöglicht Ihnen, die Unterstützung für bestimmte neue Sprach- und Bibliotheksfeatures zu deaktivieren, die Ihren vorhandenen Code stören können, der mit einer bestimmten Version des Sprachstandards kompatibel ist. Standardmäßig ist **/std:c++14** angegeben, womit Features von Sprache und Standardbibliotheken deaktiviert sind, die sich in späteren Versionen des C++-Sprachstandards finden. Verwenden Sie **/std:c++17**, um die spezifischen Features und das Verhalten gemäß dem C++17-Standard zu aktivieren. Um explizit die aktuell implementierten Features von Compiler und Standardbibliotheken zu aktivieren, die für den nächsten Entwurf des Standards vorgeschlagen sind, verwenden Sie **/std:c++latest**. Alle C ++ 20 Features erfordern **/Std: c ++ neueste**; Wenn die Implementierung abgeschlossen ist, wird ein neues **/Std: c ++ 20** Option wird aktiviert.

Die Standardoption **/std:c++14** aktiviert den Satz der C++14-Features, die vom MSVC-Compiler implementiert werden. Diese Option deaktiviert Compiler- und Standardbibliotheksunterstützung für Features, die in aktuelleren Versionen des Sprachstandards geändert oder neu sind, mit Ausnahme einiger C++17-Features, die bereits in früheren Releases des MSVC-Compilers implementiert waren. Um Breaking Changes für Benutzer zu vermeiden, die bereits Abhängigkeiten mit den in Visual Studio 2015 Update 2 verfügbaren Features implementiert haben, bleiben diese Features aktiviert, wenn die Option **/std:c++14** angegeben wird:

- [Regeln für „auto“ mit „braced-init-lists“](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3922.html)

- [typename in Vorlagen-Vorlagenparameter](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4051.html)

- [Entfernen von Trigraphen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4086.html)

- [Attribute für Namespaces und Enumeratoren](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4266.html)

- [u8-Zeichenliterale](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4267.html)

Weitere Informationen zu den aktivierten C++14- und C++17-Features, wenn **/std:c++14** angegeben ist, finden Sie die Anmerkungen in [Visual C++-Sprachkonformität](../../overview/visual-cpp-language-conformance.md).

Die Option **/std:c++17** aktiviert den vollständigen Satz der C++17-Features, die vom MSVC-Compiler implementiert werden. Diese Option deaktiviert die Unterstützung von Compiler- und Standardbibliotheken für Features, die in Versionen des Arbeitsentwurfs und Fehlerbehebungsaktualisierungen des C++-Standards nach C++17 neu sind oder geändert wurden.

Die Option **/std:c++latest** aktiviert die Sprach- und Bibliotheksfeatures nach C++17, die aktuell im Compiler und den Bibliotheken aktiviert sind. Dies schließt möglicherweise Features aus dem C++20-Arbeitsentwurf und Fehleraktualisierungen des C++-Standards, die nicht in C++17 enthalten sind, ebenso wie experimentelle Vorschläge für den Entwurfsstandard ein. Eine Liste der unterstützten Sprach- und Bibliotheksfeatures finden Sie unter [Neuerungen bei Visual C++](../../overview/what-s-new-for-visual-cpp-in-visual-studio.md). Die Option **/std:c++latest** aktiviert keine Features, die der Kontrolle durch den Schalter **/experimental** unterstehen, müssen diese aber möglicherweise aktivieren.

> [!IMPORTANT]
> Die Compiler- und Bibliotheksfeatures, die durch **/std:c++latest** aktiviert werden, stellen Features dar, die möglicherweise in einem zukünftigen C++-Standard vorkommen, jedoch auch C++20-Features, die bereits genehmigt sind. Features, die nicht genehmigt wurden, unterliegen Breaking Changes oder der Entfernung ohne Benachrichtigung und werden „wie besehen“ zur Verfügung gestellt. 

Die während einer C++-Kompilierung wirksame **/std**-Option kann mithilfe des Präprozessormakros [\_MSVC\_LANG](../../preprocessor/predefined-macros.md) bestimmt werden. Weitere Informationen finden Sie unter [Präprozessormakros](../../preprocessor/predefined-macros.md).

Die Optionen **/std:c++14** und **/std:c++latest** stehen von Visual Studio 2015 Update 3 an zur Verfügung. Die Option **/std:c++17** steht von Visual Studio 2017, Version 15.3, an zur Verfügung. Wie bereits oben angemerkt, wird ein Teil des Verhaltens nach dem C++17-Standard mit der Option **/std:c++14** aktiviert, alle anderen C++17-Features werden aber mit **/std:c++17** aktiviert. C++20-Features werden mit **/std:latest** aktiviert, bis die Implementierung abgeschlossen ist.

> [!NOTE]
> Abhängig von der MSVC-Compilerversion oder der Updateebene, sind C++17-Features möglicherweise nicht vollständig implementiert oder nicht in vollem Umfang kompatibel, wenn Sie die **/std:c++17**-Optionen angeben. Eine Übersicht der C++-Sprachkonformität in Visual C++ nach Releaseversion finden Sie unter [Visual C++-Sprachkonformität](../../overview/visual-cpp-language-conformance.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Wählen Sie **Konfigurationseigenschaften**, **C/C++** , **Sprache**aus.

1. Wählen Sie unter **C++-Sprachstandard** in der Dropdownliste den zu unterstützenden Sprachstandard und dann **OK** oder **Übernehmen** aus, um Ihre Änderungen zu speichern.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
