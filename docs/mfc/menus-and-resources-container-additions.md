---
title: "Men&#252;s und Ressourcen: Containererweiterungen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "IDP_OLE_INIT_FAILED"
  - "IDP_FAILED_TO_CREATE"
  - "VK_ESCAPE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Zugriffstastentabellen [C++], Containeranwendungen"
  - "Zugriffstastentabelle für Anwendungen [C++]"
  - "CONTAIN-Lernprogramm"
  - "IDP_FAILED_TO_CREATE-Makro"
  - "IDP_OLE_INIT_FAILED-Makro"
  - "Linksmenu-Element"
  - "OLE-Container, Menüs und Ressourcen"
  - "Visuelle Bearbeitung, Anwendungsmenüs und Ressourcen"
  - "VK_ESCAPE-Taste"
ms.assetid: 425448be-8ca0-412e-909a-a3a9ce845288
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Men&#252;s und Ressourcen: Containererweiterungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel beschreibt die Änderungen, die an den Menüs und anderen Ressourcen in einer Containeranwendung mit visueller Bearbeitung vorgenommen werden müssen.  
  
 In den Containeranwendungen müssen zwei Typen Änderungen vorgenommen werden: vorhandenen Ressourcen zur Unterstützungsvisuellen bearbeitungen in ole und zur Einführung von neuen Ressourcen verwendet für direkte Aktivierung.  Wenn Sie im Anwendungs\-Assistenten verwenden, um Ihre Containeranwendung zu erstellen, werden diese Schritte für Sie ausgeführt, jedoch erfordern möglicherweise etwas Anpassung.  
  
 Wenn Sie nicht den Anwendungs\-Assistenten verwenden, sollten Sie OCLIENT.RC, das Ressourcenskript Betrachten für die OCLIENT\-Beispielanwendung, Verdeutlichung diese Änderungen implementiert werden.  Siehe das Beispiel [OCLIENT](../top/visual-cpp-samples.md) MFC\-OLE.  
  
 Themen beschrieben in diesem Artikeleinschließung:  
  
-   [Container\-Menü\-Hinzufügungen](#_core_container_menu_additions)  
  
-   [Zugriffstastentabellen\-Hinzufügungen](#_core_container_application_accelerator_table_additions)  
  
-   [Zeichenfolgentabellen\-Hinzufügungen](#_core_string_table_additions_for_container_applications)  
  
##  <a name="_core_container_menu_additions"></a> Container\-Menü\-Hinzufügungen  
 Sie müssen die folgenden Elemente im Menü Bearbeiten hinzufügen:  
  
|Element|Zweck|  
|-------------|-----------|  
|**Neues Objekt den**|Öffnet das Objektdialogfeld OLE INSERT, um ein verknüpftes oder eingebettetes Element in das Dokument einzufügen.|  
|**Pasten\-Link**|Fügt einen Link für Element in der Zwischenablage in das Dokument ein.|  
|**OLE\-Verb**|Ruft das ausgewählten primäre Verb des Elements auf.  Der Text des Menüelements ändert, um das primäre Verb des ausgewählten Elements an.|  
|**Links**|Öffnet das OLE\-Bearbeitungs\-Linkdialogfeld, um vorhandene verknüpfte Elemente zu ändern.|  
  
 Zusätzlich zu den Änderungen, die in diesem Artikel aufgeführt sind, muss die AFXOLECL.RC Quelldatei enthalten, das für die Microsoft Foundation Class\-Bibliotheks\-Implementierung erforderlich ist.  Einfüge\- neue Objekt ist die einzige erforderliche Menühinzufügung.  Andere Elemente können hinzugefügt werden, die, die hier aufgeführt sind, die gängigsten.  
  
 Sie müssen ein neues Menü für Ihre Containeranwendung erstellen, wenn Sie direkte Aktivierung von enthaltenden Elementen unterstützen möchten.  Dieses Menü besteht aus derselben Menü und Fensterpopupmenüs verwendet haben, wenn Dateien geöffnet sind, enthält jedoch zwei Trennzeichen, die zwischen ihnen abgelegt werden.  Diese Trennzeichen werden verwendet, um anzugeben, wo das Element des Servers \(Komponente\) \(Anwendung\) seine Menüs platzieren soll, wenn es an der Stelle aktiviert ist.  Weitere Informationen über diese Menüzusammenführungstechnik, finden Sie unter [Menüs und Ressourcen: Zusammenführen von Menüs](../mfc/menus-and-resources-menu-merging.md).  
  
##  <a name="_core_container_application_accelerator_table_additions"></a> Containeranwendungs\-Zugriffstastentabellen\-Hinzufügungen  
 Kleine Änderungen an den Zugriffstastentabellenressourcen einer Containeranwendung sind erforderlich, wenn Sie direkte Aktivierung unterstützen.  Die ersten Änderung ermöglicht dem Benutzer, die Escape\-Taste \(ESC\) zu drücken um den Modus der direkten Bearbeitung abbrechen.  Fügen Sie den folgenden Eintrag der Hauptzugriffstastentabelle hinzu:  
  
|ID|Key|Typ|  
|--------|---------|---------|  
|**ID\_CANCEL\_EDIT\_CNTR**|VK\_ESCAPE|**VIRTKEY**|  
  
 Die zweite Änderung ist, eine neue Zugriffstastentabelle zu erstellen, die zur neuen Menüressource entspricht, die für direkte Aktivierung erstellt wird.  Diese Tabelle enthält Einträge für die Datei\- und Fenstermenüs neben dem Eintrag **VK\_ESCAPE** oben.  Im folgenden Beispiel ist die Zugriffstastentabelle, die für direkte Aktivierung im MFC\-Beispiel [CONTAINER](../top/visual-cpp-samples.md) erstellt wird:  
  
|ID|Key|Typ|  
|--------|---------|---------|  
|`ID_FILE_NEW`|STRG\+N|**VIRTKEY**|  
|`ID_FILE_OPEN`|STRG\+O|**VIRTKEY**|  
|**ID\_FILE\_SAVE**|STRG\+S|**VIRTKEY**|  
|**ID\_FILE\_PRINT**|STRG\+P|**VIRTKEY**|  
|**ID\_NEXT\_PANE**|VK\_F6|**VIRTKEY**|  
|**ID\_PREV\_PANE**|SHIFT\+VK\_F6|**VIRTKEY**|  
|**ID\_CANCEL\_EDIT\_CNTR**|VK\_ESCAPE|**VIRTKEY**|  
  
##  <a name="_core_string_table_additions_for_container_applications"></a> Zeichenfolgentabellen\-Hinzufügungen für Containeranwendungen  
 Die meisten Änderungen an Zeichenfolgentabellen für Containeranwendungen entsprechen den zusätzlichen Menüelementen, die in der [Container\-Menü\-Hinzufügungen](#_core_container_menu_additions) erwähnt werden.  Sie stellen den Text, der in der Statusleiste angezeigt wird, wenn jedes Menüelement angezeigt wird.  Als Beispiel sind hier die Zeichenfolgentabelleneinträge, die der Anwendungs\-Assistent generiert:  
  
|ID|Zeichenfolge|  
|--------|------------------|  
|**IDP\_OLE\_INIT\_FAILED**|OLE\-Initialisierungsfehler.  Stellen Sie sicher, dass die OLE\-Bibliotheken in der richtigen Version vorliegen.|  
|**IDP\_FAILED\_TO\_CREATE**|Fehler beim Erstellen des Objekts.  Stellen Sie sicher, dass das Objekt in die Systemregistrierung eingegeben wird.|  
  
## Siehe auch  
 [Menüs und Ressourcen \(OLE\)](../mfc/menus-and-resources-ole.md)   
 [Menüs und Ressourcen: Servererweiterungen](../mfc/menus-and-resources-server-additions.md)