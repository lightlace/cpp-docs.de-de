---
title: Buildsystemänderungen
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
ms.openlocfilehash: 742b018ae96ff706336a81b49e1d8e5fb954d9b7
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57425444"
---
# <a name="build-system-changes"></a>Buildsystemänderungen

Das MSBuild-System wird verwendet, um Visual C++-Projekte zu erstellen. In Visual Studio 2008 und früheren Versionen wurde jedoch das VCBuild-System verwendet. Bestimmte Dateitypen und die Konzepte, die von VCBuild abhing nicht vorhanden, oder im aktuellen System unterschiedlich dargestellt werden. Dieses Dokument erläutert die Unterschiede im aktuellen Buildsystem.

## <a name="vcproj-is-now-vcxproj"></a>.vcproj lautet jetzt VCXPROJ.

Projektdateien verwenden nicht mehr die VCPROJ-Dateinamenerweiterung. Visual Studio konvertiert automatisch die Projektdateien, die von einer früheren Version von Visual C++ in das Format erstellt wurden, die vom aktuellen System verwendet wird. Weitere Informationen dazu, wie Sie ein Projekt manuell zu aktualisieren, finden Sie unter [/Upgrade (devenv.exe)](/visualstudio/ide/reference/upgrade-devenv-exe).

In der aktuellen Version ist die Dateinamenerweiterung für eine Projektdatei VCXPROJ.

## <a name="vsprops-is-now-props"></a>vsprops ist jetzt PROPS

In früheren Versionen eine *Projekteigenschaftenblatt* ist eine XML-basierte Datei, die eine vsprops-Dateinamenerweiterung aufweist. Ein Projekteigenschaftenblatt können Sie die Schalter für Buildtools wie Compiler- oder Linkeroptionen anzugeben und benutzerdefinierte Makros zu erstellen.

In der aktuellen Version ist die Dateinamenerweiterung für ein Projekteigenschaftenblatt props.

## <a name="custom-build-rules-and-rules-files"></a>Benutzerdefinierte Buildregeln und rules-Dateien

In früheren Versionen eine *Regeldatei* ist eine XML-basierte Datei, die eine rules-Dateinamenerweiterung aufweist. Eine Regeldatei können Sie die benutzerdefinierte Buildregeln erstellen und integrieren sie in den Buildprozess eines Visual C++-Projekts. Eine benutzerdefinierte Buildregel, die eine oder mehrere Dateierweiterungen zugeordnet sein kann, können Sie die Eingabedateien zu einem Tool zu übergeben, die eine erstellt ein oder mehrere Ausgabedateien.

In dieser Version werden die benutzerdefinierten Buildregeln werden durch drei Dateitypen, XML, props- und targets, anstatt eine rules-Datei dargestellt. Wenn eine rules-Datei, die mit einer früheren Version von Visual C++ erstellt wurde, auf die aktuelle Version migriert wird, entsprechende XML, props- und TARGETS-Dateien erstellt und in Ihrem Projekt zusammen mit der ursprünglichen rules-Datei gespeichert.

> [!IMPORTANT]
>  In der aktuellen Version unterstützt die Erstellung neuer Regeln die IDE nicht. Aus diesem Grund ist die einfachste Möglichkeit, eine Regeldatei aus einem Projekt verwenden, die mit einer früheren Version von Visual C++ erstellt wurde das Projekt auf die aktuelle Version zu migrieren.

## <a name="inheritance-macros"></a>Vererbung von Makros

In früheren Versionen der **$(Inherit)** Makro gibt die Reihenfolge, in der geerbte Eigenschaften angezeigt werden, in der Befehlszeile aus, das vom Projektbuildsystem besteht. Die **$(NoInherit)** Makro bewirkt, dass alle Vorkommen von $(Inherit) ignoriert werden und alle Eigenschaften, die andernfalls, nicht geerbt werden sollen, geerbt werden sollen. Beispielsweise verursacht der $(inherit)-makro standardmäßig mit angegebene Dateien die [/i (Zusätzliche Includeverzeichnisse)](../build/reference/i-additional-include-directories.md) -Compileroption, die über die Befehlszeile angefügt werden soll.

In der aktuellen Version wird die Vererbung durch Angeben des Werts einer Eigenschaft als die Verkettung von ein oder mehrere Literalwerte und Eigenschaftenmakros unterstützt. Die **$(Inherit)** und **$(NoInherit)** Makros werden nicht unterstützt.

Im folgenden Beispiel wird eine durch Semikolons getrennte Liste an eine Eigenschaft auf einer Eigenschaftenseite zugewiesen. Die Liste enthält die Verkettung von den  *\<Wert >* Literal und der Wert von der `MyProperty` -Eigenschaft, die mithilfe der Makro-Schreibweise erfolgt, **$(**  <em>MyProperty</em>**)**.

```
Property=<value>;$(MyProperty)
```

## <a name="vcxprojuser-files"></a>. vcxproj.user-Dateien

Eine Datei (. vcxproj.user) speichert benutzerspezifische Eigenschaften für das Beispiel, Debuggen und Bereitstellen von Einstellungen. Die VCXPROJ für alle Projekte für einen bestimmten Benutzer.

## <a name="vcxprojfilters-file"></a>. vcxproj.filters Datei

Wenn **Projektmappen-Explorer** dient zum Hinzufügen einer Datei zu einem Projekt, das die Filterdatei (. vcxproj.filters) definiert die Position in der **Projektmappen-Explorer** Strukturansicht anzeigen, die Datei hinzugefügt wird, basierend auf der Dateierweiterung.

## <a name="vc-directories-settings"></a>VC++-Verzeichnisse-Einstellungen

Visual C++-Verzeichnisse-Einstellungen angegeben sind, auf die [VC++ Directories Property Page](../ide/vcpp-directories-property-page.md). In früheren Versionen von Visual Studio Verzeichnisse-Einstellungen gelten pro Benutzer, und die Liste der ausgeschlossenen Verzeichnissen in der Datei sysincl.dat angegeben ist.

Sie können die VC++-Verzeichnisse-Einstellungen nicht ändern, wenn das Ausführen [Devenv/resetsettings](/visualstudio/ide/reference/resetsettings-devenv-exe) an der Befehlszeile eingeben. Außerdem können nicht geändert werden die beim Öffnen der **Tools** Menü klicken Sie auf **Einstellungen importieren und exportieren**, und wählen Sie dann die **alle Einstellungen zurücksetzen** Option.

Migrieren Sie Einstellungen für VC++-Verzeichnisse aus einer VSSETTINGS-Datei, die von einer früheren Version von Visual C++ erstellt wird. Öffnen der **Tools** Menü klicken Sie auf **Einstellungen importieren und exportieren**Option **ausgewählte umgebungseinstellungen importieren**, und befolgen Sie dann die Anweisungen im Assistenten. Oder beim start von Visual Studio zum ersten Mal auf die **Standardumgebungseinstellungen auswählen** wählen Sie im Dialogfeld **geeigneten Einstellungen von einer früheren Version migrieren, und wenden Sie sie zusätzlich zu den Standardeinstellungen unten ausgewählten**.

## <a name="see-also"></a>Siehe auch

[MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)
