---
title: Buildsystemänderungen in Visual Studio 2010
ms.date: 11/04/2016
f1_keywords:
- vc.msbuild.changes
helpviewer_keywords:
- Build system changes, project file (.vcxprog)
- Build system changes, custom build rules
- Build system changes, MSBuild
- MSBuild, build system changes
- Build system changes, .vsprops
- Build system changes, $(Inherit)
- Build system changes, $(NoInherit)
ms.assetid: e564d95f-a6cc-4d97-b57e-1a71daf66f4a
ms.openlocfilehash: c3e51aa7e5a4346137e94191b551b0d53452e460
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2019
ms.locfileid: "65449006"
---
# <a name="build-system-changes"></a>Buildsystemänderungen

Zum Erstellen von C++-Projekten in Visual Studio wird das MSBuild-System verwendet. In Visual Studio 2008 und früheren Releases wurde jedoch das VCBuild-System verwendet. Bestimmte Dateitypen und Konzepte, die von VCBuild abhängig waren, sind entweder nicht mehr vorhanden und werden im aktuellen System anders umgesetzt. In diesem Artikel werden die Unterschiede im aktuellen Buildsystem behandelt.

## <a name="vcproj-is-now-vcxproj"></a>VCPROJ ist nun VCXPROJ

Projektdateien verwenden nicht mehr die VCPROJ-Erweiterung. Visual Studio konvertiert Projektdateien, die mit einem vorherigen Release von Visual C++ erstellt wurden, automatisch in das Format, das das aktuelle System verwendet. Weitere Informationen zum manuellen Upgrade von Projekten finden Sie unter [/Upgrade (devenv.exe)](/visualstudio/ide/reference/upgrade-devenv-exe).

Im aktuellen Release lautet die Erweiterung für Projektdateien VCXPROJ.

## <a name="vsprops-is-now-props"></a>VSPROPS ist nun PROPS

In früheren Releases waren *Projekteigenschaftenblätter* XML-basierte Dateien mit der Erweiterung VSPROPS. Mit einem Projekteigenschaftenblatt können Sie Parameter für Buildtools festlegen, z. B. Compiler oder Linker, und benutzerdefinierte Makros erstellen.

Im aktuellen Release lautet die Erweiterung für Projekteigenschaftenblätter PROPS.

## <a name="custom-build-rules-and-rules-files"></a>Benutzerdefinierte Buildregeln und RULES-Dateien

In früheren Releases waren *Regeldateien* XML-basierte Dateien mit der Erweiterung RULES. Mit Regeldateien können Sie benutzerdefinierte Buildregeln definieren und diese in den Buildvorgang eines C++-Projekts in Visual Studio integrieren. Mit benutzerdefinierten Buildregeln, die mehreren Erweiterungen zugeordnet sein können, können Sie Eingabedateien an ein Tool übergeben, das mindestens eine Ausgabedatei erstellt.

In diesem Release werden benutzerdefinierte Buildregeln von den drei Dateitypen XML, PROPS und TARGETS dargestellt, anstatt von einer RULES-Datei. Wenn eine RULES-Datei, die mit einem früheren Release von Visual C++ erstellt wurde, zum aktuellen Release migriert wird, werden entsprechende XML-, PROPS- und TARGETS-Dateien erstellt und mit der ursprünglichen RULES-Datei im Projekt gespeichert.

> [!IMPORTANT]
>  Im aktuellen Release unterstützt die IDE das Erstellen neuer Regeln nicht. Aus diesem Grund, besteht die einfachste Möglichkeit darin, eine Regeldatei aus einem Projekt zu verwenden, das mit einem früheren Release von Visual C++ erstellt wurde, um das Projekt zum aktuellen Release zu migrieren.

## <a name="inheritance-macros"></a>Vererbungsmakros

In früheren Releases hat das Makro **$(Inherit)** die Reihenfolge festgelegt, in der geerbte Eigenschaften in der Befehlszeile angezeigt werden, die aus dem Projektbuildsystem besteht. Mit dem Makro **$(NoInherit)** werden alle Vorkommnisse von „$(Inherit)“ ignoriert und Eigenschaften, die andernfalls geerbt werden würden, werden nicht geerbt. Durch das Makro „$(Inherit)“ werden beispielsweise Dateien, die mithilfe der Compileroption [/I (Additional Include Directories)](../build/reference/i-additional-include-directories.md) (/I (Zusätzliche Includeverzeichnisse)) festgelegt werden, an die Befehlszeile angefügt.

Im aktuellen Release wird die Vererbung durch Festlegen des Werts einer Eigenschaft als Verkettung von Literalwerten und Eigenschaftenmakros unterstützt. Die Makros **$(Inherit)** und **$(NoInherit)** werden nicht unterstützt.

Im folgenden Beispiel wird einer Eigenschaft auf einer Eigenschaftenseite eine durch Semikolons getrennte Liste zugewiesen. Die Liste besteht aus der Verkettung des Literals *\<Wert>* und des Werts der `MyProperty`-Eigenschaft, auf den mithilfe der Makronotation **$(** <em>MyProperty</em> **)** zugegriffen wird.

```
Property=<value>;$(MyProperty)
```

## <a name="vcxprojuser-files"></a>VCXPROJ.USER-Dateien

Benutzerdateien (VCXPROJ.USER) speichern benutzerspezifische Eigenschaften, z. B. Debug- und Bereitstellungseinstellungen. Die VCXPROJ.USER-Datei wird für einen bestimmten Benutzer auf alle Projekte angewendet.

## <a name="vcxprojfilters-file"></a>VCXPROJ.FILTERS-Dateien

Wenn der **Projektmappen-Explorer** zum Hinzufügen einer Datei zu einem Projekt verwendet wird, definiert die Filterdatei (VCXPROJ.FILTERS) anhand der Erweiterung, wo die Datei in der Gesamtstrukturansicht des **Projektmappen-Explorers** hinzugefügt wird.

## <a name="vc-directories-settings"></a>Einstellungen für VC++-Verzeichnisse

Die Einstellungen von Visual C++-Verzeichnissen werden auf der [Eigenschaftenseite für VC++-Verzeichnisse](../ide/vcpp-directories-property-page.md) festgelegt. In früheren Releases von Visual Studio galten Verzeichniseinstellungen pro Benutzer, und die Liste ausgeschlossener Verzeichnisse wurde in der SYSINCL.DAT-Datei angegeben.

Sie können die VC++-Verzeichniseinstellungen nicht ändern, wenn Sie [devenv /resetsettings](/visualstudio/ide/reference/resetsettings-devenv-exe) in der Befehlszeile ausführen. Außerdem können Sie die Einstellungen nicht ändern, indem Sie das Menü **Extras** öffnen, auf **Einstellungen importieren/exportieren** klicken und dann die Option **Alle Einstellungen zurücksetzen** auswählen.

Migrieren Sie die VC++-Verzeichniseinstellungen aus einer VSSETTINGS-Datei, die mit einem früheren Release von Visual C++ erstellt wurde. Öffnen Sie hierzu das Menü **Extras**, klicken Sie auf **Einstellungen importieren/exportieren**, klicken Sie dann auf **Ausgewählte Umgebungseinstellungen importieren**, und führen Sie anschließend die Anweisungen des Assistenten aus. Alternativ können Sie beim ersten Start von Visual Studio im Dialogfeld **Standardumgebungseinstellungen auswählen** die Option **Gültige Einstellungen aus einer vorherigen Version migrieren und zusätzlich zu den unten ausgewählten Standardeinstellungen übernehmen** auswählen.

## <a name="see-also"></a>Siehe auch

[MSBuild on the Command Line – C++ (C++: MSBuild in der Befehlszeile)](../build/msbuild-visual-cpp.md)
