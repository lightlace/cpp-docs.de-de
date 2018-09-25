---
title: Projekt- und Projektmappendateien | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.files.projectandsolution
dev_langs:
- C++
helpviewer_keywords:
- project files [C++]
- file types [C++], makefiles
- .sdf, browsing database file
- Makefile projects
- browsing database file, .sdf
- file types [C++], project files
ms.assetid: 5823b954-36cf-42d3-8fd5-25bab3ef63d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f52041ef8049e0e7ad4b12677ac1599b2cfd5669
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46408185"
---
# <a name="project-and-solution-files"></a>Projekt- und Projektmappendateien

Die folgenden Dateien werden erstellt, wenn Sie ein Projekt in Visual Studio erstellen. Sie werden verwendet, um die Projektdateien in der Projektmappe zu verwalten.

|Dateiname|Speicherort für das Verzeichnis|Speicherort für den Projektmappen-Explorer|Beschreibung |
|--------------|------------------------|--------------------------------|-----------------|
|*Solname*.sln|*Projname*|Wird im Projektmappen-Explorer nicht angezeigt.|Die *Projektmappendatei*. Es werden alle Elemente eines Projekts oder mehrerer Projekte in einer einzigen Projektmappe organisiert.|
|*Projname*.suo|*Projname*|Wird im Projektmappen-Explorer nicht angezeigt.|Die Datei mit den *Projektmappenoptionen*. Darin werden die Anpassungen für die Projektmappe gespeichert, damit jedes Mal, wenn Sie ein Projekt oder eine Datei in der Projektmappe öffnen, die gewünschte Darstellung und das gewünschte Verhalten vorhanden ist.|
|*Projname*.vcxproj|*Projname*|Wird im Projektmappen-Explorer nicht angezeigt.|Die *Projektdatei*. Die für das Projekt spezifischen Informationen werden darin gespeichert. (In früheren Versionen hieß diese Datei *Projname*.vcproj oder *Projname*.dsp.) Ein Beispiel für eine Visual C++-Projektdatei finden Sie unter [Project Files (Projektdateien)](../ide/project-files.md).|
|*Projname*.vcxitems|*Projname*|Wird im Projektmappen-Explorer nicht angezeigt.|Die *Projektdatei mit freigegebenen Elementen*. Das Projekt wird nicht erstellt.  Stattdessen kann von einem anderen C++-Projekt auf das Projekt verwiesen werden, und die darin enthaltenen Dateien werden Bestandteil des Buildprozesses des verweisenden Projekts. Dies kann zum Freigeben von allgemeinem Code für plattformübergreifende C++-Projekte verwendet werden.|
|*Projname*.sdf|*Projname*|Wird im Projektmappen-Explorer nicht angezeigt.|Die Datei zum *Durchsuchen der Datenbank*. Sie unterstützt Such-und Navigationsfeatures, wie z.B. **Gehe zu Definition**, **Alle Verweise suchen** und **Klassenansicht**. Sie wird durch die Analyse der Headerdateien generiert.|
|*Projname.* vcxproj.filters|*Projname*|Wird im Projektmappen-Explorer nicht angezeigt.|Die *Filterdatei*. Sie gibt an, wo eine Datei, die der Projektmappe hinzugefügt wird, abgelegt werden soll. Zum Beispiel wird eine H-Datei im Knoten **Headerdateien** abgelegt.|
|*Projname.* vcxproj.user|*Projname*|Wird im Projektmappen-Explorer nicht angezeigt.|Die *Migrationsbenutzerdatei*. Nachdem ein Projekt von Visual Studio 2008 migriert wurde, enthält diese Datei Informationen, die aus einer beliebigen .vsprops-Datei konvertiert wurden.|
|*Projname*.idl|*Projname*|Quelle|(Projektspezifisch) Enthält den Interface Description Language (IDL)-Quellcode für eine Steuerelement-Typbibliothek. Diese Datei wird von Visual C++ verwendet, um eine Typbibliothek zu generieren. Mithilfe der generierten Bibliothek wird die Schnittstelle des Steuerelements anderen Automatisierungsclients zur Verfügung gestellt. Weitere Informationen finden Sie im Windows SDK unter [Interface Definition (IDL) File (Schnittstellendefinitionsdatei)](/windows/desktop/Rpc/the-interface-definition-language-idl-file).|
|Readme.txt|*Projname*|Projekt|Die *Infodatei*. Sie wird vom Anwendungs-Assistenten generiert und beschreibt die Dateien in einem Projekt.|

## <a name="see-also"></a>Siehe auch

[Für Visual C++-Projekte erstellte Dateitypen](../ide/file-types-created-for-visual-cpp-projects.md)