---
title: "Projekt- und Projektmappendateien | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.files.projectandsolution"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SDF, Durchsuchen von Datenbankdateien"
  - "Durchsuchen von Datenbankdateien, SDF"
  - "Dateitypen [C++], Makefiles"
  - "Dateitypen [C++], Projektdateien"
  - "Makefile-Projekte"
  - "Projektdateien [C++]"
ms.assetid: 5823b954-36cf-42d3-8fd5-25bab3ef63d9
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Projekt- und Projektmappendateien
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die folgenden Dateien werden erstellt, wenn Sie ein Projekt in Visual Studio erstellen.  Sie werden verwendet, um die Projektdateien in der Projektmappe zu verwalten.  
  
|Dateiname|Speicherort für das Verzeichnis|Speicherort für den Projektmappen\-Explorer|Beschreibung|  
|---------------|-------------------------------------|-------------------------------------------------|------------------|  
|*Solname*.sln|*Projektname*|Wird im Projektmappen\-Explorer nicht angezeigt.|Die *Projektmappen*datei.  Es werden alle Elemente eines Projekts oder mehrerer Projekte in einer einzigen Projektmappe organisiert.|  
|*Projname*.suo|*Projektname*|Wird im Projektmappen\-Explorer nicht angezeigt.|Die Datei mit den *Projektmappenoptionen*.  Darin werden die Anpassungen für die Projektmappe gespeichert, damit jedes Mal, wenn Sie ein Projekt oder eine Datei in der Projektmappe öffnen, die gewünschte Darstellung und das gewünschte Verhalten vorhanden ist.|  
|*Projname*.vcxproj|*Projektname*|Wird im Projektmappen\-Explorer nicht angezeigt.|Die *Projekt*datei.  Die für das Projekt spezifischen Informationen werden darin gespeichert.  \(In früheren Versionen hieß diese Datei *Projname*.vcproj oder *Projname*.dsp.\) Ein Beispiel für eine Visual C\+\+\-Projektdatei finden Sie unter [Projektdateien](../ide/project-files.md).|  
|*Projname*.sdf|*Projektname*|Wird im Projektmappen\-Explorer nicht angezeigt.|Die Datei zum *Durchsuchen von Datenbanken*.  Sie unterstützt Such\-und Navigationsfunktionen, wie beispielsweise **Gehe zu Definition**, **Alle Verweise suchen** und **Klassenansicht**.  Sie wird durch die Analyse der Headerdateien generiert.|  
|*Projname.*vcxproj.filters|*Projektname*|Wird im Projektmappen\-Explorer nicht angezeigt.|Die *Filter*datei.  Sie gibt an, wo eine Datei, die der Projektmappe hinzugefügt wird, abgelegt werden soll.  Beispielsweise wird eine .h\-Datei im Knoten **Headerdateien** abgelegt.|  
|*Projname.*vcxproj.user|*Projektname*|Wird im Projektmappen\-Explorer nicht angezeigt.|Die *Migrationsbenutzer*datei.  Nachdem ein Projekt von Visual Studio 2008 migriert wurde, enthält diese Datei Informationen, die aus einer beliebigen .vsprops\-Datei konvertiert wurden.|  
|*Projname*.idl|*Projektname*|Quelle|\(Projektspezifisch\) Enthält den Interface Description Language \(IDL\)\-Quellcode für eine Steuerelement\-Typbibliothek.  Diese Datei wird von Visual C\+\+ verwendet, um eine Typbibliothek zu generieren.  Mithilfe der generierten Bibliothek wird die Schnittstelle des Steuerelements anderen Automatisierungsclients zur Verfügung gestellt.  Weitere Informationen finden Sie unter [Schnittstellendefinitionsdatei](http://msdn.microsoft.com/library/windows/desktop/aa378712) im [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)].|  
|Readme.txt|*Projektname*|Projekt|Die *Readme*\-Datei.  Sie wird vom Anwendungs\-Assistenten generiert und beschreibt die Dateien in einem Projekt.|  
  
## Siehe auch  
 [Für Visual C\+\+\-Projekte erstellte Dateitypen](../ide/file-types-created-for-visual-cpp-projects.md)