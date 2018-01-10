---
title: "Buildsystemänderungen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.msbuild.changes
dev_langs: C++
helpviewer_keywords:
- Build system changes, project file (.vcxprog)
- Build system changes, custom build rules
- Build system changes, MSBuild
- MSBuild, build system changes
- Build system changes, .vsprops
- Build system changes, $(Inherit)
- Build system changes, $(NoInherit)
ms.assetid: e564d95f-a6cc-4d97-b57e-1a71daf66f4a
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 59d30e2afd07c21cb42dbc2b9109d7547d6c5b9f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="build-system-changes"></a>Buildsystemänderungen
Das MSBuild-System wird verwendet, um Visual C++-Projekte zu erstellen. In Visual Studio 2008 und früheren Versionen wurde jedoch die VCBuild-System verwendet. Bestimmte Dateitypen und Konzepte, die von VCBuild abhängig sind nicht vorhanden, oder im aktuellen System anders dargestellt. Dieses Dokument beschreibt die Unterschiede im aktuellen Buildsystem.  
  
## <a name="vcproj-is-now-vcxproj"></a>.vcproj lautet jetzt VCXPROJ.  
 Projektdateien verwenden nicht mehr die VCPROJ-Dateinamenerweiterung. Automatisch konvertiert Visual Studio-Projektdateien, die von einer früheren Version von Visual C++ in das Format erstellt wurden, die vom aktuellen System verwendet wird. Weitere Informationen dazu, wie Sie ein Projekt manuell aktualisieren, finden Sie unter [/Upgrade (devenv.exe)](/visualstudio/ide/reference/upgrade-devenv-exe).  
  
 In der aktuellen Version wird die Dateinamenerweiterung für eine Projektdatei VCXPROJ.  
  
## <a name="vsprops-is-now-props"></a>vsprops lautet jetzt PROPS.  
 In früheren Versionen eine *Projekteigenschaftenblatt* ist eine XML-basierten Datei, die eine beliebigen .vsprops-Dateinamenerweiterung aufweist. Ein Projekteigenschaftenblatt können Sie die Schalter für den Build-Tools, z. B. Compiler oder Linker angeben und benutzerdefinierte Makros erstellen.  
  
 In der aktuellen Version wird die Dateinamenerweiterung für ein Projekteigenschaftenblatt props.  
  
## <a name="custom-build-rules-and-rules-files"></a>Benutzerdefinierte Buildregeln und rules-Dateien  
 In früheren Versionen eine *Regeldatei* ist eine XML-basierten Datei, die eine rules-Dateinamenerweiterung aufweist. Eine Regeldatei können Sie benutzerdefinierte Buildregeln definieren und in den Buildprozess eines Visual C++-Projekts zu integrieren. Eine benutzerdefinierte Buildregel, die eine oder mehrere Dateinamenerweiterungen zugeordnet sein kann, können Sie die Eingabedateien zu einem Tool zu übergeben, der einem Vorgang erstellt ein oder mehrere Ausgabedateien.  
  
 In dieser Version werden benutzerdefinierte Buildregeln durch drei Dateitypen, XML, props- und targets, anstelle einer rules-Datei dargestellt. Wenn eine rules-Datei, die mit einer früheren Version von Visual C++ erstellt wurde, auf die aktuelle Version migriert wird, werden entsprechende XML, props- und TARGETS-Dateien erstellt und in Ihrem Projekt zusammen mit der ursprünglichen rules-Datei gespeichert.  
  
> [!IMPORTANT]
>  In der aktuellen Version der [!INCLUDE[TLA2#tla_ide](../build/includes/tla2sharptla_ide_md.md)] unterstützt nicht die Erstellung neuer Regeln. Aus diesem Grund ist die einfachste Möglichkeit, eine Regeldatei aus einem Projekt verwenden, die mit einer früheren Version von Visual C++ erstellt wurde das Projekt auf die aktuelle Version zu migrieren.  
  
## <a name="inheritance-macros"></a>Vererbung von Makros  
 In früheren Versionen der **$(Inherit)** Makro gibt die Reihenfolge der geerbte Eigenschaften in der Befehlszeile, die vom Projektbuildsystem besteht. Die **$(NoInherit)** Makro bewirkt, dass alle Vorkommen von $(Inherit) ignoriert werden soll, und alle Eigenschaften, die andernfalls, nicht geerbt werden würde, geerbt werden. Das $(inherit)-makro verursacht beispielsweise standardmäßig mit angegebene Dateien der [/i (Zusätzliche Includeverzeichnisse)](../build/reference/i-additional-include-directories.md) (Compileroption), die über die Befehlszeile angefügt werden soll.  
  
 In der aktuellen Version wird Vererbung unterstützt, durch den Wert einer Eigenschaft als Verkettung der ein oder mehrere Literalwerte und Eigenschaftenmakros angeben. Die **$(Inherit)** und **$(NoInherit)** Makros werden nicht unterstützt.  
  
 Im folgenden Beispiel wird eine Eigenschaft auf einer Eigenschaftenseite eine durch Semikolons getrennte Liste zugewiesen. Die Liste enthält die Verkettung von der  *\<Wert >* Literal und der Wert des der `MyProperty` -Eigenschaft, die mithilfe der Schreibweise Makro erfolgt, **$(**  *MyProperty***)**.  
  
```  
Property=<value>;$(MyProperty)  
```  
  
## <a name="vcxprojuser-files"></a>. vcxproj.user-Dateien  
 Eine Datei (. vcxproj.user) speichert benutzerspezifische Eigenschaften für Einstellungen Beispiel, debugging und Bereitstellungen. Die VCXPROJ für alle Projekte für einen bestimmten Benutzer.  
  
## <a name="vcxprojfilters-file"></a>. vcxproj.filters Datei  
 Wenn **Projektmappen-Explorer** wird verwendet, um eine Datei eines Projekts, die Filterdatei hinzufügen (. vcxproj.filters) definiert, an welcher Stelle der **Projektmappen-Explorer** Strukturansicht die Datei zuerst hinzugefügt wird, basierend auf der entsprechenden dateinamenserweiterung.  
  
## <a name="vc-directories-settings"></a>VC++-Verzeichnisse-Einstellungen  
 Visual C++-Verzeichnissen-Einstellungen angegeben sind, auf die [VC++-Verzeichnisse Eigenschaftenseite](../ide/vcpp-directories-property-page.md). In früheren Versionen von Visual Studio Verzeichnisse Einstellungen gelten pro Benutzer und die Liste der ausgeschlossenen Verzeichnisse in der Datei sysincl.dat angegeben ist.  
  
 Sie können die VC++-Verzeichnisse-Einstellungen nicht ändern, wenn das Ausführen [Devenv/resetsettings](/visualstudio/ide/reference/resetsettings-devenv-exe) in der Befehlszeile. Sie auch die können nicht geändert, wenn Sie öffnen die **Tools** Menü klicken Sie auf **Einstellungen importieren und exportieren**, und wählen Sie dann die **alle Einstellungen zurücksetzen** Option.  
  
 Migrieren Sie VC++-Verzeichnisse Einstellungen aus einer VSSETTINGS-Datei, die von einer früheren Version von Visual C++ erstellt wird. Öffnen der **Tools** Menü klicken Sie auf **Einstellungen importieren und exportieren**Option **ausgewählte umgebungseinstellungen importieren**, und befolgen Sie dann die Anweisungen im Assistenten. Oder beim start von Visual Studio zum ersten Mal auf die **Standardumgebungseinstellungen auswählen** wählen Sie im Dialogfeld **geeigneten Einstellungen aus einer früheren Version migrieren, und sie zusätzlich zu den Standardeinstellungen anzuwenden unten ausgewählten**.  
  
## <a name="see-also"></a>Siehe auch  
 [MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)