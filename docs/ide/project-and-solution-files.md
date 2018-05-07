---
title: Projekt- und Projektmappendateien | Microsoft Docs
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
ms.openlocfilehash: 08cf1386ef177823c37bc285392309ec47f3c464
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="project-and-solution-files"></a>Projekt- und Projektmappendateien
Die folgenden Dateien werden erstellt, wenn Sie ein Projekt in Visual Studio erstellen. Sie werden verwendet, um die Projektdateien in der Projektmappe zu verwalten.  
  
|Dateiname|Speicherort für das Verzeichnis|Speicherort für den Projektmappen-Explorer|Beschreibung|  
|--------------|------------------------|--------------------------------|-----------------|  
|*Solname*sln|*Projektname*|Wird im Projektmappen-Explorer nicht angezeigt.|Die *Lösung* Datei. Es werden alle Elemente eines Projekts oder mehrerer Projekte in einer einzigen Projektmappe organisiert.|  
|*Projektname*SUO|*Projektname*|Wird im Projektmappen-Explorer nicht angezeigt.|Die *Projektmappenoptionen* Datei. Darin werden die Anpassungen für die Projektmappe gespeichert, damit jedes Mal, wenn Sie ein Projekt oder eine Datei in der Projektmappe öffnen, die gewünschte Darstellung und das gewünschte Verhalten vorhanden ist.|  
|*Projektname*VCXPROJ|*Projektname*|Wird im Projektmappen-Explorer nicht angezeigt.|Die *Projekt* Datei. Die für das Projekt spezifischen Informationen werden darin gespeichert. (In früheren Versionen hieß diese Datei *Projname*.vcproj oder *Projname*DSP.) Ein Beispiel einer Visual C++-Projektdatei finden Sie unter [Projektdateien](../ide/project-files.md).|  
|*Projektname*.vcxitems|*Projektname*|Wird im Projektmappen-Explorer nicht angezeigt.|Die *freigegebenen Projekt* Datei. Dieses Projekt wird nicht erstellt.  Stattdessen kann das Projekt von einem anderen C++-Projekt verwiesen werden, und seine Dateien werden als Bestandteil des Buildprozesses das verweisende Projekt. Dies kann zum Freigeben von gemeinsamen Codes mit plattformübergreifenden C++-Projekten verwendet werden.|
|*Projektname*.sdf|*Projektname*|Wird im Projektmappen-Explorer nicht angezeigt.|Die *Durchsuchen von Datenbanken* Datei. Sie unterstützt Such- und Navigationsfunktionen Funktionen wie z. B. **Gehe zu Definition**, **alle Verweise suchen**, und **Klassenansicht**. Sie wird durch die Analyse der Headerdateien generiert.|  
|*Projektname.* vcxproj.filters|*Projektname*|Wird im Projektmappen-Explorer nicht angezeigt.|Die *Filter* Datei. Sie gibt an, wo eine Datei, die der Projektmappe hinzugefügt wird, abgelegt werden soll. Z. B. wird eine .h-Datei abgelegt, der **Headerdateien** Knoten.|  
|*Projektname.* vcxproj.user|*Projektname*|Wird im Projektmappen-Explorer nicht angezeigt.|Die *Migrationsbenutzer* Datei. Nachdem ein Projekt von Visual Studio 2008 migriert wurde, enthält diese Datei Informationen, die aus einer beliebigen .vsprops-Datei konvertiert wurden.|  
|*Projektname*IDL|*Projektname*|Quelle|(Projektspezifisch) Enthält den Interface Description Language (IDL)-Quellcode für eine Steuerelement-Typbibliothek. Diese Datei wird von Visual C++ verwendet, um eine Typbibliothek zu generieren. Mithilfe der generierten Bibliothek wird die Schnittstelle des Steuerelements anderen Automatisierungsclients zur Verfügung gestellt. Weitere Informationen finden Sie unter [IDL (Interface Definition)-Datei](http://msdn.microsoft.com/library/windows/desktop/aa378712) im Windows SDK.|  
|Readme.txt|*Projektname*|Projekt|Die *Infodatei* Datei. Sie wird vom Anwendungs-Assistenten generiert und beschreibt die Dateien in einem Projekt.|  
  
## <a name="see-also"></a>Siehe auch  
 [Für Visual C++-Projekte erstellte Dateitypen](../ide/file-types-created-for-visual-cpp-projects.md)