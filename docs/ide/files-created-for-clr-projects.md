---
title: Für CLR-Projekte erstellte Dateien | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Visual C++ projects, CLR programming
- .NET applications, C++
ms.assetid: 59ae9020-5f26-4ad0-bbdd-97c2e2023a20
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b9d66c3f55164a743bc395dc5e9b48f8bcd57654
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="files-created-for-clr-projects"></a>Für CLR-Projekte erstellte Dateien
Wenn Sie Visual C++-Vorlagen verwenden, um Ihre Projekte erstellen, werden mehrere Dateien erstellt, je nachdem welcher, die Vorlage Sie verwenden. Die folgende Tabelle enthält alle Dateien, die von Projektvorlagen für .NET Framework-Projekte erstellt werden.  
  
|Dateiname|DateiBeschreibung|  
|---------------|----------------------|  
|AssemblyInfo.cpp|Die Datei mit Informationen (d. h., Attribute, Dateien, Ressourcen, Typen, Versionsinformationen, Signaturinformationen usw.) zum Ändern der Assemblymetadaten des Projekts. Weitere Informationen finden Sie unter [Assemblyinhalte](/dotnet/framework/app-domains/assembly-contents).|  
|*Projektname*ASMX|Eine Textdatei, verweisen auf verwaltete Klassen, die die Funktionalität des XML-Webdiensts zu kapseln.|  
|*Projektname*cpp|Die Hauptquelldatei und Eintrag zeigen in der Anwendung, die Visual Studio für Sie erstellt. Diese Datei identifiziert die DLL-Datei und den Namespace des Projekts. Fügen Sie eigenen Code in diese Datei ein.|  
|*Projektname*.vsdisco|Eine Bereitstellung XML-Datei mit Links zu weiteren Ressourcen, die den XML-Webdienst beschreiben.|  
|*Projektname*h|Die Haupt-Include-Datei für das Projekt, die alle Deklarationen, globalen Symbole enthält, und `#include` Direktiven für die anderen Header-Dateien.|  
|*Projektname*sln|Die Projektmappendatei, die in der Entwicklungsumgebung verwendet werden, um alle Elemente des Projekts in einer einzelnen Projektmappe zu organisieren.|  
|*Projektname*SUO|Datei mit den Projektmappenoptionen in der Entwicklungsumgebung verwendet.|  
|*Projektname*VCXPROJ|Die Projektdatei, die in der Entwicklungsumgebung, die speichert die Informationen, die speziell für dieses Projekt verwendet.|  
|ReadMe.txt|Eine Datei, die jede Datei im Projekt enthaltenen Dateien von der Vorlage erstellten beschreibt.|