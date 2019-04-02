---
title: / Std (Standardversion Sprache festlegen)
ms.date: 11/26/2018
f1_keywords:
- /std
- -std
- VC.Project.VCCLCompilerTool.CppLanguageStandard
ms.assetid: 0acb74ba-1aa8-4c05-b96c-682988dc19bd
ms.openlocfilehash: 32c63240f578b6170ae351cdf0cd1628167464b6
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58779741"
---
# <a name="std-specify-language-standard-version"></a>/ Std (Standardversion Sprache festlegen)

Enable unterstützt C++-Sprachfeatures, aus der angegebenen Version des C++-Sprachstandard.

## <a name="syntax"></a>Syntax

> /std:\[c++14\|c++17\|c++latest]

## <a name="remarks"></a>Hinweise

Die **/Std** Option ist in Visual Studio 2017 und höher verfügbar. Es wird verwendet, um versionsspezifische ISO C++ programming Language-Standardfunktionen aktiviert, während der Kompilierung des Codes zu steuern. Diese Option können Sie zum Deaktivieren der Unterstützung für bestimmte neuen Sprach- und bibliotheksunterstützung-Funktionen, die einen Umbruch von vorhandenen Code, der eine bestimmte Version der Sprache entspricht standard. In der Standardeinstellung **/Std: c ++ 14** angegeben wird, wodurch die Sprache und die Features der Standardbibliothek finden Sie in höheren Versionen der Programmiersprache C++ standard deaktiviert. Verwendung **/Std: c ++ 17** C ++ 17-Standard-spezifischen Funktionen und das Verhalten zu aktivieren. Verwenden Sie zum expliziten Aktivieren der derzeit implementierten Compiler und die Features der Standardbibliothek, die für den nächsten Draft Standard vorgeschlagene **/Std: c ++ neueste**.

Der Standardwert **/Std: c ++ 14** Option aktiviert die C ++ 14-Funktionen von der MSVC-Compiler implementiert. Diese Option deaktiviert, Compiler und Standardbibliothek-Unterstützung für Funktionen, die geändert werden oder neuer in neueren Versionen der Sprache standard, mit Ausnahme von einigen C ++ 17-Features bereits in früheren Versionen von der MSVC-Compiler implementiert. Um zu vermeiden, wichtige Änderungen für Benutzer, die bereits die Abhängigkeiten zu den Features zur Verfügung, ab dem Visual Studio 2015 Update 2 erstellt haben, diese Funktionen bleiben aktiviert, wenn die **/Std: c ++ 14** angegeben wird:

- [Regeln für Auto "mit" braced-Init-lists](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3922.html)

- [TypeName in Vorlagen-Vorlagenparametern](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4051.html)

- [Entfernen von Trigraphen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4086.html)

- [Attribute für Namespaces und Enumeratoren](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4266.html)

- [U8-Zeichenliterale](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4267.html)

Weitere Informationen auf die C ++ 14 und C ++ 17-Features aktiviert sind, wenn **/Std: c ++ 14** ist angegeben, siehe Hinweise im [Visual C++-Sprachkonformität](../../overview/visual-cpp-language-conformance.md).

Die **/Std: c ++ 17** Option ermöglicht den vollständigen Satz von C ++ 17-Features, von der MSVC-Compiler implementiert. Diese Option deaktiviert die Unterstützung von Compiler- und Standardbibliotheken für Features, die in Versionen des Arbeitsentwurfs und Fehlerbehebungsaktualisierungen des C++-Standards nach C++17 neu sind oder geändert wurden.

Die **/Std: c ++ neueste** Option ermöglicht die Post-C ++ 17 Sprach- und bibliotheksunterstützung-Funktionen, die derzeit im Compiler und Bibliotheken implementiert. Diese können Funktionen aus der C ++ 20 Arbeitsentwurfs und fehlerbehebungsaktualisierungen Updates des C++-Standards enthalten, die nicht in C ++ 17 sowie experimentelle Angebote für den Entwurfsstandard enthalten sind. Eine Liste der unterstützten Sprachen und Features der Standardbibliothek, finden Sie unter [neuerungen bei Visual C++](../../overview/what-s-new-for-visual-cpp-in-visual-studio.md). Die **/Std: c ++ neueste** Option keine Funktionen, die von überwachten aktiviert die **/ experimentelle** wechseln, jedoch möglicherweise erforderlich, um sie zu aktivieren.

> [!IMPORTANT]
> Die aktivierte Funktionen für Compiler und -Bibliothek **/Std: c ++ neueste** als bereitgestellt werden – ist und ohne Unterstützung. Sie unterliegen aktuellen Änderungen bzw. ohne vorherige Ankündigung. Sie dienen als Vorschau von Sprachfunktionen, die in der nächsten Version des Standards angezeigt werden kann, aber der Standard ist noch In Bearbeitung. Verwenden Sie **/Std: c ++ 17** um die Features im neuesten ISO C++-Standard zu verwenden.

Die **/Std** faktisch während einer C++-Kompilierung die Option kann mithilfe der erkannt werden die [ \_MSVC\_LANG](../../preprocessor/predefined-macros.md) Präprozessor-Makro. Weitere Informationen finden Sie unter [Präprozessor Makros](../../preprocessor/predefined-macros.md).

Die **/Std: c ++ 14** und **/Std: c ++ neueste** Optionen sind verfügbar ab der in Visual C++ 2015 Update 3. Die **/Std: c ++ 17** Option ist ab, die in Visual C++ 2017 Version 15.3 verfügbar. Wie bereits erwähnt, einige C ++ 17-standard wird Verhalten aktiviert, indem die **/Std: c ++ 14** Option, aber alle anderen C ++ 17-Features werden aktiviert, indem **/Std: c ++ 17**.

> [!NOTE]
> Abhängig von der MSVC-Compiler Version oder ein Update, bestimmte C ++ 14 und C ++ 17-Features möglicherweise nicht vollständig implementiert oder vollständig-konforme Funktion bei der Angabe der **/Std: c ++ 14** oder **/Std: c ++ 17** Optionen. Z. B. der Visual C++ 2017 RTM-Compiler unterstützt nicht vollständig C ++ 14-konformen `constexpr`, sfinae für Ausdrücke, oder 2-Phasen Namenssuche. Eine Übersicht über C++-sprachkonformität in Visual C++ von der endgültigen Produktversion, finden Sie unter [Visual C++-Sprachkonformität](../../overview/visual-cpp-language-conformance.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie **Konfigurationseigenschaften**, **C/C++-**, **Sprache**.

1. In **Standard der Sprache C++**, wählen Sie den Sprachstandard zu unterstützen, die aus der Dropdownliste aus, und wählen Sie dann **OK** oder **übernehmen** zum Speichern der Änderungen.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
