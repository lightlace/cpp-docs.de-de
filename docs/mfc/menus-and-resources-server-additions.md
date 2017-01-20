---
title: "Men&#252;s und Ressourcen: Servererweiterungen"
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
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Zugriffstastentabellen [C++], Serveranwendungen"
  - "IDP_OLE_INIT_FAILED-Makro"
  - "OLE-Initialisierungsfehler"
  - "OLE-Serveranwendungen, Menüs und Ressourcen"
  - "OLE-Server für visuelle Bearbeitung"
  - "Ressourcen [MFC], Serveranwendungen"
  - "Serveranwendungen, Zugriffstastentabellen"
  - "Serveranwendungen, OLE-Menüs und Ressourcen"
  - "Server, Menüerweiterungen"
  - "Zeichenfolgenbearbeitung, Anwendungen für visuelle Bearbeitung"
  - "Zeichenfolgentabellen, Anwendungen für visuelle Bearbeitung"
  - "Visuelle Bearbeitung, Anwendungsmenüs und Ressourcen"
ms.assetid: 56ce9e8d-8f41-4db8-8dee-e8b0702d057c
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Men&#252;s und Ressourcen: Servererweiterungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel beschreibt die Änderungen, die an den Menüs und anderen Ressourcen in einer visuellen Anwendung des Bearbeitungsservers vorgenommen werden müssen \(Komponente\).  Eine Serveranwendung erfordert viele Erweiterungen der Menüstruktur und anderen Ressourcen, da er in einem von drei Modi gestartet werden kann: eigenständig eingebettet oder angezeigt.  Wie im Artikel [Menüs und Ressourcen \(OLE\)](../mfc/menus-and-resources-ole.md) beschrieben, können Sie maximal vier Sätzen von Menüs.  Alle vier werden für eine MDI\-FULLServer\-Anwendung verwendet, während nur drei für ein miniserver verwendet werden.  Der Anwendungs\-Assistent erstellt das Menülayout, das für den Typ des Servers erforderlich ist, den Sie möchten.  Einige Anpassung ist möglicherweise erforderlich.  
  
 Wenn Sie nicht den Anwendungs\-Assistenten verwenden, sollten Sie HIERSVR.RC, das Ressourcenskript Betrachten für die MFC\-Beispielanwendung [HIERSVR](../top/visual-cpp-samples.md), zum diese Änderungen implementiert werden.  
  
 Themen beschrieben in diesem Artikeleinschließung:  
  
-   [Server\-Menü\-Hinzufügungen](#_core_server_menu_additions)  
  
-   [Zugriffstastentabellen\-Hinzufügungen](#_core_server_application_accelerator_table_additions)  
  
-   [Zeichenfolgentabellen\-Hinzufügungen](../mfc/menus-and-resources-container-additions.md)  
  
-   [Miniserver\-Hinzufügungen](#_core_mini.2d.server_additions)  
  
##  <a name="_core_server_menu_additions"></a> Server\-Menü\-Hinzufügungen  
 Anwendungen des Servers \(Komponente\) müssen die Menüressourcen verfügen, die zur Unterstützungsvisuellen bearbeitungen in ole hinzugefügt werden.  Die verwendeten Menüs, wenn die Anwendung in eigenständigen Modus ausgeführt wird, müssen nicht geändert werden, müssen Sie jedoch Menüressourcen zwei neuen hinzufügen, bevor die Anwendung erstellt: ein, um von direkter Aktivierung unterstützt und einen, um den Server zu unterstützen, die vollständig geöffnet ist.  Beide Menüressourcen werden durch die miniserver doppelklicken und Anwendungen.  
  
-   Um direkte Aktivierung unterstützt wird, müssen Sie eine Menüressource erstellen die Menüressource stark ähnelt, wenn sie in eigenständigen Modus verwendet wird ausgeführt wird.  Der Unterschied in dieses Menüs ist, dass die Datei\- und Navigationshosts \(sowie alle anderen Menüelemente, die aus der Anwendung angewendet werden und die Daten nicht\) angewendet.  Die Containeranwendung stellt diese Menüelemente.  Weitere Informationen sowie ein Beispiel, finden diese Menüzusammenführungstechnik, den Artikel [Menüs und Ressourcen: Zusammenführen von Menüs](../mfc/menus-and-resources-menu-merging.md).  
  
-   Um geöffnete vollständig Aktivierung zu unterstützen, müssen Sie eine Menüressource erstellen, die zur Menüressource fast identisch ist, die beim Ausführen in eigenständigen Modus verwendet wird ausgeführt wird.  Die einzige Änderung an dieser Menüressource ist, dass einige andere Elemente formuliert werden, um der Tatsache an, der den Server auf ein Element angewendet wird, das in einem Verbunddokument eingebettet wird.  
  
 Zusätzlich zu den Änderungen, die in diesem Artikel aufgeführt sind, muss die Ressourcendatei AFXOLESV.RC enthalten, das für die Microsoft Foundation Class\-Bibliotheks\-Implementierung erforderlich ist.  Diese Datei ist im Einschließungsunterverzeichnis MFC\- \\.  
  
##  <a name="_core_server_application_accelerator_table_additions"></a> Serveranwendungs\-Zugriffstastentabellen\-Hinzufügungen  
 Zwei neue Zugriffstastentabellenressourcen müssen in Serveranwendungen hinzugefügt werden; Sie entsprechen direkt zu neuen zuvor beschriebenen Menüressourcen.  Die erste Zugriffstastentabelle wird verwendet, wenn die Serveranwendung an der Stelle aktiviert ist.  Sie enthält alle Einträge in der Zugriffstastentabelle der Ansicht außer die gebunden an den Datei\- und Fenstermenüs.  
  
 Die zweite Tabelle ist eine fast genaue Kopie der Zugriffstastentabelle der Ansicht.  Alle Änderungen vorgenommen parallelen der Unterschiede im vollständig geöffneten Menü erwähnt in [Server\-Menü\-Hinzufügungen](#_core_server_menu_additions).  
  
 Ein Beispiel für diesen Zugriffstastentabellenänderungen, vergleichen Sie die **IDR\_HIERSVRTYPE\_SRVR\_IP** und **IDR\_HIERSVRTYPE\_SRVR\_EMB** Zugriffstastentabellen mit **IDR\_MAINFRAME** in der HIERSVR.RC\-Datei, die im Beispiel [HIERSVR](../top/visual-cpp-samples.md) MFC\-OLE enthalten ist.  Die Dateien und Fensterzugriffstasten fehlen der direkten Tabelle und fordern Kopien davon sind in der eingebetteten Tabelle.  
  
##  <a name="_core_string_table_additions_for_server_applications"></a> Zeichenfolgentabellen\-Hinzufügungen für Serveranwendungen  
 Nur eine Zeichenfolgentabellenhinzufügung ist in einer Serveranwendung \- eine Zeichenfolge anzugeben erforderlich, dass die OLE\-Initialisierung fehlgeschlagen ist.  Als Beispiel ist hier der Eintrag aus einer Zeichenfolgentabelle, den der Anwendungs\-Assistent generiert:  
  
|ID|Zeichenfolge|  
|--------|------------------|  
|**IDP\_OLE\_INIT\_FAILED**|OLE\-Initialisierungsfehler.  Stellen Sie sicher, dass die OLE\-Bibliotheken in der richtigen Version vorliegen.|  
  
##  <a name="_core_mini.2d.server_additions"></a> Miniserver\-Hinzufügungen  
 Die gleichen Hinzufügungen wenden miniservers als die, die weiter oben für Vollservers aufgeführt werden.  Da ein miniserver nicht in eigenständigen Modus ausgeführt werden kann, ist sein Hauptmenü viel kleiner.  Das Hauptmenü, das vom Anwendungs\-Assistenten erstellt wird, ist nur eine Menü Datei und enthält nur die Elemente Beendigungen und ungefähr.  Eingebettete direkte und Menüs und Zugriffstasten für miniservers sind identisch mit denen für Vollservers.  
  
## Siehe auch  
 [Menüs und Ressourcen \(OLE\)](../mfc/menus-and-resources-ole.md)   
 [Menüs und Ressourcen: Menüs schachteln](../mfc/menus-and-resources-menu-merging.md)