---
title: "BSCMAKE-Referenz"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BSC-Dateien, Erstellen"
  - "Browserinformationsdateien (.bsc), Erstellen"
  - "Browserfenster"
  - "BSC-Dateien, Erstellen"
  - "BSCMAKE"
  - "BSCMAKE, Referenz"
  - "Microsoft Browse Information Maintenance-Dienstprogramm"
ms.assetid: b97ad994-1355-4809-98db-6abc12c6fb13
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# BSCMAKE-Referenz
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

> [!WARNING]
>  Obwohl BSCMAKE weiterhin mit Visual Studio installiert wird, wird es nicht mehr von der IDE verwendet.  Seit Visual Studio 2008 werden Browse\- und Symbolinformationen automatisch in einer SQL Server\-.SDF\-Datei im Projektmappenordner gespeichert.  
  
 Das Microsoft Browse Information Maintenance\-Programm \(BSCMAKE.EXE\) erstellt eine neue Browseinformationsdatei \(.bsc\) aus SBR\-Dateien, die während der Kompilierung erstellt wurden.  Sie zeigen eine Browseinformationsdatei im Objektkatalog an.  Informationen über den Objektkatalog finden Sie unter [Navigieren im Objektkatalog](assetId:///53eb91aa-08c6-4299-8e3c-a877ae8d0c55).  
  
 Wenn Sie ein Programm erstellen, können Sie eine Browseinformationsdatei für das Programm automatisch mithilfe von BSCMAKE zum Erstellen der Datei erstellen.  Sie müssen nicht wissen, wie BSCMAKE ausgeführt wird, wenn Sie Ihre Browseinformationsdatei in der Visual C\+\+\-Entwicklungsumgebung erstellen.  Vielleicht möchten Sie dieses Thema jedoch lesen, um die verfügbaren Optionen kennenzulernen.  
  
 Wenn Sie ein Programm außerhalb der Entwicklungsumgebung erstellen, können Sie weiterhin eine benutzerdefinierte BSC\-Datei erstellen, die Sie in der Umgebung untersuchen können.  Führen Sie BSCMAKE für die SBR\-Dateien aus, die Sie während der Kompilierung erstellt haben.  
  
> [!NOTE]
>  Sie können dieses Tool nur von der [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]\-Eingabeaufforderung aus starten.  Sie können es nicht von einer Systemeingabeaufforderung oder vom Datei\-Explorer aus starten.  
  
 Dieser Abschnitt schließt folgende Themen ein:  
  
-   [Erstellen von Browseinformationsdateien: Übersicht](../../build/reference/building-browse-information-files-overview.md)  
  
-   [Erstellen einer BSC\-Datei](../../build/reference/building-a-dot-bsc-file.md)  
  
-   [BSCMAKE\-Befehlszeile](../../build/reference/bscmake-command-line.md)  
  
-   [BSCMAKE\-Befehlszeile](../../build/reference/bscmake-command-file-response-file.md)  
  
-   [BSCMAKE\-Optionen](../../build/reference/bscmake-options.md)  
  
-   [BSCMAKE\-Exitcodes](../../build/reference/bscmake-exit-codes.md)  
  
## Siehe auch  
 [C\/C\+\+\-Buildtools](../../build/reference/c-cpp-build-tools.md)