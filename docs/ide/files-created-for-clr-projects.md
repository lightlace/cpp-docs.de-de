---
title: "Für CLR-Projekte erstellte Dateien | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Visual C++ projects, CLR programming
- .NET applications, C++
ms.assetid: 59ae9020-5f26-4ad0-bbdd-97c2e2023a20
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a4abf5415e9b252a7cc92408fb273d226106fc16
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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