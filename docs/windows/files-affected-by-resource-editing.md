---
title: "Files Affected by Resource Editing"
ms.custom: na
ms.date: "12/14/2016"
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
  - "resource editing"
  - "resources [Visual Studio], editing"
ms.assetid: d0820df1-ba84-40ac-bce9-29ea5ee7e3f8
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Files Affected by Resource Editing
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Visual Studio\-Umgebung arbeitet während der Sitzung zur Bearbeitung von Ressourcen mit den in der folgenden Tabelle angegebenen Dateien.  
  
|Dateiname|Beschreibung|  
|---------------|------------------|  
|Resource.h|Durch die Entwicklungsumgebung generierte Headerdatei; enthält Symboldefinitionen.|  
|Filename.aps|Binäre Version der aktuellen Ressourcenskriptdatei; zum schnellen Laden verwendet.<br /><br /> .rc\- oder resource.h\-Dateien werden von Ressourcen\-Editoren nicht direkt gelesen.  Der Ressourcencompiler kompiliert sie in .aps\-Dateien, die von den Ressourcen\-Editoren genutzt werden.  Diese Datei ist ein Kompilierungsschritt und speichert nur symbolische Daten.  Wie bei einer normalen Kompilierung werden Informationen, die nicht symbolisch sind \(z. B. Kommentare\) während der Kompilierung verworfen.  Sobald die .aps\-Datei nicht mehr mit der .rc\-Datei synchron ist, wird die .rc\-Datei neu generiert \(z. B. überschreibt der Ressourcen\-Editor beim Speichern die .rc\-Datei und resource.h\-Datei\).  Alle Änderungen an den Ressourcen selbst bleiben in der .rc\-Datei, aber Kommentare gehen immer verloren, sobald die .rc\-Datei überschrieben wird.  Informationen zur Erhaltung von Kommentaren finden Sie unter [Einfügen von Ressourcen zur Kompilierungszeit](../windows/how-to-include-resources-at-compile-time.md).|  
|.rc|Ressourcenskriptdatei, die Skript für die Ressourcen im aktuellen Projekt enthält.  Diese Datei wird bei jedem Speichern durch die .aps\-Datei überschrieben.|  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Anforderungen  
 Win32  
  
## Siehe auch  
 [Resource Files](../mfc/resource-files-visual-studio.md)