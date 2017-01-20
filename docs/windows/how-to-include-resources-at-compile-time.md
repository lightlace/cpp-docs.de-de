---
title: "How to: Include Resources at Compile Time"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vs.resvw.resource.including"
  - "vc.resvw.resource.including"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "compiling source code, including resources"
  - "comments [C++], compiled files"
  - "resources [Visual Studio], including at compile time"
  - "projects [C++], including resources"
  - "#include directive"
  - "include directive (#include)"
ms.assetid: 357e93c2-0a29-42f9-806f-882f688b8924
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# How to: Include Resources at Compile Time
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Es ist für gewöhnlich einfach und intuitiv mit der Standardanordnung sämtlicher Ressourcen in einer Ressourcenskriptdatei \(.rc\) zu arbeiten.  Sie können jedoch Ressourcen in anderen Dateien zu Ihrem aktuellen Projekt zum Zeitpunkt der Kompilierung hinzufügen, indem Sie sie im Feld **Kompilierzeitdirektiven** im Dialogfeld [Ressourcenincludes](../windows/resource-includes-dialog-box.md) auflisten.  
  
 Es gibt verschiedene Gründe für das Platzieren von Ressourcen in einer Datei, die von der RC\-Hauptdatei abweicht:  
  
-   Zum Hinzufügen von Kommentaren zu Ressourcenanweisungen, die beim Speichern der RC\-Datei nicht gelöscht werden.  
  
     .rc\- oder resource.h\-Dateien werden von Ressourcen\-Editoren nicht direkt gelesen.  Der Ressourcencompiler kompiliert sie in .aps\-Dateien, die von den Ressourcen\-Editoren genutzt werden.  Diese Datei ist ein Kompilierungsschritt und speichert nur symbolische Daten.  Wie bei einer normalen Kompilierung werden Informationen, die nicht symbolisch sind \(z. B. Kommentare\) während der Kompilierung verworfen.  Sobald die .aps\-Datei nicht mehr mit der .rc\-Datei synchron ist, wird die .rc\-Datei neu generiert \(z. B. überschreibt der Ressourcen\-Editor beim Speichern die .rc\-Datei und resource.h\-Datei\).  Alle Änderungen an den Ressourcen selbst bleiben in der .rc\-Datei, aber Kommentare gehen immer verloren, sobald die .rc\-Datei überschrieben wird.  
  
-   Zum Einbeziehen von bereits entwickelten und getesteten Ressourcen, die nicht weiter geändert werden müssen.  \(Einbezogene Dateien ohne RC\-Erweiterung können durch die Ressourcen\-Editoren nicht bearbeitet werden.\)  
  
-   Zum Einbeziehen von Ressourcen, die durch mehrere unterschiedliche Projekte verwendet werden oder die Bestandteil eines Quellcode\-Versionssteuerungssystems sind und daher an einem zentralen Speicherort vorhanden sein müssen, wo sich die Änderungen auf alle Projekte auswirken.  
  
-   Zum Einbeziehen von Ressourcen \(beispielsweise RCDATA\-Ressourcen\), die ein benutzerdefiniertes Format aufweisen.  RCDATA\-Ressourcen weisen möglicherweise spezielle Anforderungen auf.  Beispielsweise können Sie einen Ausdruck für das Feld „nameID“ nicht als Wert verwenden.  Weitere Informationen finden Sie in der Dokumentation zu [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)].  
  
 Wenn Sie über Abschnitte in Ihren vorhandenen RC\-Dateien verfügen, die diese Bedingungen erfüllen, sollten Sie die Abschnitte in mindestens einer getrennten RC\-Datei platzieren und sie in Ihrem Projekt mithilfe des Dialogfelds [Ressourcenincludes](../windows/resource-includes-dialog-box.md) einbeziehen.  Die im „\\res2“\-Unterverzeichnis eines neuen Projekts erstellte „*Projektname*.rc2“\-Datei wird für diesen Zweck verwendet.  
  
### So beziehen Sie Ressourcen In Ihr Projekt zum Zeitpunkt der Kompilierung ein  
  
1.  Platzieren Sie die Ressourcen in einer Ressourcenskriptdatei mit einem eindeutigen Dateinamen.  Verwenden Sie nicht „*projektname*.rc“, da es sich hierbei um den für die Haupt\-Ressourcenskriptdatei verwendeten Dateinamen handelt.  
  
2.  Klicken Sie mit der rechten Maustaste auf die RC\-Datei \(in [Ressourcenansicht](../windows/resource-view-window.md)\), und wählen Sie **Ressourcenincludes** aus dem Kontextmenü aus.  
  
3.  Fügen Sie im Feld **Kompilierzeitdirektiven** die Compilerdirektiver [\#include](../preprocessor/hash-include-directive-c-cpp.md) hinzu, um die neue Ressourcendatei in der Hauptressourcendatei in der Entwicklungsumgebung einzubeziehen.  
  
     Die auf diese Weise in die Dateien einbezogenen Ressourcen werden zum Bestandteil Ihrer ausführbaren Datei zum Zeitpunkt der Kompilierung.  Sie stehen nicht direkt für die Bearbeitung oder Änderung zur Verfügung, wenn Sie die RC\-Hauptdatei Ihres Projekts bearbeiten.  Sie müssen einbezogene RC\-Dateien einzeln öffnen.  Einbezogene Dateien ohne RC\-Erweiterung können durch die Ressourcen\-Editoren nicht bearbeitet werden.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Anforderungen  
  
 Win32  
  
## Siehe auch  
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)