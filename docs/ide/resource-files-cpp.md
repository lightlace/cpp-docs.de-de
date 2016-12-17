---
title: "Ressourcendateien (C++)"
ms.custom: na
ms.date: "12/03/2016"
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
  - "Dateitypen [C++], Ressourcendateien"
  - "Ressourcendateien"
  - "Ressourcen [C++]"
ms.assetid: 338a4a0f-0c62-4ef1-a34f-5d86262d93a4
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Ressourcendateien (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ressourcen sind Schnittstellenelemente, die Informationen für den Benutzer bereitstellen.  Bitmaps, Symbole, Symbolleisten und Cursor zählen zu den Ressourcen.  Einige Ressourcen können bearbeitet werden, um eine Aktion auszuführen, z. B. um eine Option aus einem Menü auszuwählen oder Daten in einem Dialogfeld einzugeben.  
  
 Weitere Informationen finden Sie unter [Arbeiten mit Ressourcen](../mfc/working-with-resource-files.md).  
  
|Dateiname|Verzeichnis|Anzeige im Projektmappen\-Explorer|Beschreibung|  
|---------------|-----------------|----------------------------------------|------------------|  
|*Projname*.rc|*Projname*|Quelldateien|Ressourcenskriptdatei für das Projekt.  Abhängig vom Projekttyp und der für das Projekt ausgewählten Unterstützung \(z. B. Symbolleisten, Dialogfelder oder HTML\) enthält die Ressourcenskriptdatei folgende Elemente:<br /><br /> -   Standardmenüdefinition<br />-   Zugriffstasten\- und Zeichenfolgentabellen<br />-   Standarddialogfeld **Info**<br />-   Weitere Dialogfelder<br />-   Symboldatei \(**res\\**Projname**.ico**\)<br />-   Versionsinformationen<br />-   Bitmaps<br />-   Symbolleiste<br />-   HTML\-Dateien<br /><br /> Die Ressourcendatei enthält die Datei **Afxres.rc** für Microsoft Foundation Class\-Standardressourcen.|  
|Resource.h|*Projname*|Headerdateien|Ressourcenheaderdatei, die Definitionen für die vom Projekt verwendeten Ressourcen enthält.|  
|*Projname*.rc2|*Projname*\\res|Quelldateien|Skriptdatei mit zusätzlichen, vom Projekt verwendeten Ressourcen.  Die RC2\-Datei kann am Anfang der projektspezifischen RC\-Datei eingefügt werden.<br /><br /> Eine RC2\-Datei ist hilfreich beim Einfügen von Ressourcen, die von mehreren verschiedenen Projekten verwendet werden.  Anstatt dieselben Ressourcen mehrere Male für verschiedene Projekte erstellen zu müssen, können Sie sie in einer RC2\-Datei speichern und diese RC2\-Datei in die RC\-Hauptdatei einfügen.|  
|*Projname*.def|*Projname*|Quelldateien|Moduldefinitionsdatei für ein DLL\-Projekt.  Bei einem Steuerelement gibt diese Datei den Namen und die Beschreibung des Steuerelements sowie die Größe des Laufzeitheaps an.|  
|*Projname*.ico|*Projname*\\res|Ressourcendateien|Symboldatei für das Projekt oder das Steuerelement.  Dieses Symbol wird angezeigt, wenn die Anwendung minimiert ist.  Darüber hinaus wird es im Feld **Info** der Anwendung verwendet.  MFC stellt standardmäßig das MFC\-Symbol und ATL standardmäßig das ATL\-Symbol bereit.|  
|*Projname*Doc.ico|*Projname*\\res|Ressourcendateien|Symboldatei für ein MFC\-Projekt, das Unterstützung für die Dokument\-\/Ansichtarchitektur umfasst.|  
|Toolbar.bmp|*Projname*\\res|Ressourcendateien|Bitmapdatei, die die Anwendung oder das Steuerelement in einer Symbolleiste oder Palette darstellt.  Diese Bitmap ist in der Ressourcendatei des Projekts enthalten.  Die ursprüngliche Symbol\- und Statusleiste werden in der **CMainFrame**\-Klasse erstellt.|  
|ribbon.mfcribbon\-ms|*Projname*\\res|Ressourcendateien|Ressourcendatei, die den XML\-Code enthält, mit dem die Schaltflächen, Steuerelemente und Attribute im Menüband definiert werden.  Weitere Informationen finden Sie unter [Menüband\-Designer \(MFC\)](../mfc/ribbon-designer-mfc.md).|  
  
## Siehe auch  
 [Für Visual C\+\+\-Projekte erstellte Dateitypen](../ide/file-types-created-for-visual-cpp-projects.md)