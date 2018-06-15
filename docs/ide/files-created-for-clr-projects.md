---
title: Für CLR-Projekte erstellte Dateien | Microsoft-Dokumentation
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
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "33334664"
---
# <a name="files-created-for-clr-projects"></a>Für CLR-Projekte erstellte Dateien
Wenn Sie Visual C++-Vorlagen verwenden, um Ihre Projekte zu erstellen, werden je nach verwendeter Vorlage mehrere Dateien erstellt. In der folgenden Tabelle werden alle Dateien aufgelistet, die von Projektvorlagen für .NET Framework-Projekte erstellt werden.  
  
|Dateiname|Dateibeschreibung|  
|---------------|----------------------|  
|AssemblyInfo.cpp|Die Datei mit Informationen (z.B. Attributen, Dateien, Ressourcen, Typen, Versionsinformationen, Signaturinformationen usw.), durch die Assemblymetadaten des Projekts geändert werden. Weitere Informationen finden Sie unter [Assemblykonzepte](/dotnet/framework/app-domains/assembly-contents).|  
|*projname*.asmx|Eine Textdatei, die auf verwaltete Klassen verweist, die die Funktionen des XML-Webdiensts kapseln.|  
|*projname*.cpp|Die Hauptquelldatei und Einstiegspunkt in die Anwendung, die von Visual Studio für Sie erstellt wurde. Diese Datei identifiziert die DLL-Datei und den Namespace des Projekts. Fügen Sie eigenen Code in diese Datei ein.|  
|*projname*.vsdisco|Eine XML-Bereitstellungsdatei mit Links zu weiteren Ressourcen, die den XML-Webdienst beschreiben.|  
|*projname*.h|Die Hauptincludedatei für das Projekt, die alle Deklarationen, globalen Symbole und `#include`-Direktiven für andere Headerdateien enthält.|  
|*projname*.sln|Die Projektmappendatei, die innerhalb der Entwicklungsumgebung verwendet wird, um alle Elemente Ihres Projekts in einer einzelnen Projektmappe zu organisieren.|  
|*projname*.suo|Die Projektmappenoptionsdatei, die in der Entwicklungsumgebung verwendet wird.|  
|*projname*.vcxproj|Die Projektdatei, die in der Entwicklungsumgebung verwendet wird und die spezifischen Informationen für dieses Projekt speichert.|  
|ReadMe.txt|Eine Datei mit einer Beschreibung der einzelnen in einem Projekt enthaltenen Dateien. Dabei werden die tatsächlichen von der Vorlage erstellten Dateinamen verwendet.|