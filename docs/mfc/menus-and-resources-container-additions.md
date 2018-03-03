---
title: "Menüs und Ressourcen: Containererweiterungen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDP_OLE_INIT_FAILED
- IDP_FAILED_TO_CREATE
- VK_ESCAPE
dev_langs:
- C++
helpviewer_keywords:
- application accelerator table [MFC]
- VK_ESCAPE key [MFC]
- IDP_FAILED_TO_CREATE macro [MFC]
- visual editing, application menus and resources
- OLE containers [MFC], menus and resources
- accelerator tables [MFC], container applications
- IDP_OLE_INIT_FAILED macro [MFC]
- CONTAIN tutorial [MFC]
- Links menu item [MFC]
ms.assetid: 425448be-8ca0-412e-909a-a3a9ce845288
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 654efeaacd08e0d2c8c51cee012fd58dcbf071ab
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="menus-and-resources-container-additions"></a>Menüs und Ressourcen: Containererweiterungen
Dieser Artikel beschreibt die Änderungen, die mit den Menüs und anderen Ressourcen in eine visuelle Bearbeitung Steuerelementcontainer-Anwendung vorgenommen werden müssen.  
  
 In containeranwendungen zwei Arten von Änderungen vorgenommen werden müssen: Änderungen an vorhandenen Ressourcen zum OLE visuelle Bearbeitung und Hinzufügen von neuen Ressourcen für die direkte Aktivierung unterstützen. Wenn Sie die Anwendungs-Assistent zum Erstellen Ihrer containeranwendung verwenden, diese Schritte werden für Sie ausgeführt werden, jedoch erfordern möglicherweise einige Anpassungen.  
  
 Wenn Sie den Anwendungsassistenten nicht verwenden, empfiehlt es sich um OCLIENT betrachten. RC, das Ressourcenskript OCLIENT-beispielanwendung, um festzustellen, wie diese Änderungen implementiert werden. Finden Sie im MFC-OLE-Beispiel [OCLIENT](../visual-cpp-samples.md).  
  
 In diesem Artikel behandelten Themen werden behandelt:  
  
-   [Container-Menüerweiterungen](#_core_container_menu_additions)  
  
-   [Accelerator Tabelle hinzufügen](#_core_container_application_accelerator_table_additions)  
  
-   [Zeichenfolge Tabelle hinzufügen](#_core_string_table_additions_for_container_applications)  
  
##  <a name="_core_container_menu_additions"></a>Container-Menüerweiterungen  
 Sie müssen die folgenden Elemente im Menü Bearbeiten hinzufügen:  
  
|Element|Zweck|  
|----------|-------------|  
|**Neues Objekt einfügen**|Öffnet das Dialogfeld OLE Objekt einfügen, um eine verknüpfte oder eingebettete Element in das Dokument eingefügt.|  
|**Verknüpfen**|Fügt einen Link zu dem Element in der Zwischenablage in das Dokument.|  
|**OLE-Verb**|Ruft das ausgewählte Element primäres Verb. Der Text des dieses Menüelement entsprechend primäre Verb des ausgewählten Elements ändert.|  
|**Links**|Öffnet das Dialogfeld OLE Verknüpfungen bearbeiten, um vorhandene verknüpfte Elemente zu ändern.|  
  
 Zusätzlich zu den Änderungen, die in diesem Artikel aufgeführt wird muss die Quelldatei AFXOLECL enthalten. RC, die für die Microsoft Foundation Class Library-Implementierung erforderlich ist. Neues Objekt einfügen ist das einzige erforderliche Menü hinzufügen. Andere Elemente können hinzugefügt werden, aber die hier aufgeführten die häufigsten Ursachen sind.  
  
 Wenn Sie direkte Aktivierung der enthaltenen Elemente unterstützen möchten, müssen Sie ein neues Menü für Ihre containeranwendung erstellen. Dieses Menü besteht aus dem gleichen Dateimenü und Fenster Popupmenüs verwendet, wenn Dateien geöffnet sind, verfügt aber über zwei Trennzeichen dazwischen eingefügt. Diese Trennzeichen werden verwendet, um anzugeben, auf dem Server (Komponente)-Element (Anwendung) Menüs bei direkt aktiviert ablegen soll. Weitere Informationen zu dieser Technik das Zusammenführen von Menüs finden Sie unter [Menüs und Ressourcen: Menüs schachteln](../mfc/menus-and-resources-menu-merging.md).  
  
##  <a name="_core_container_application_accelerator_table_additions"></a>Anwendung Accelerator Tabelle Containererweiterungen  
 Kleine Änderungen an eine Steuerelementcontainer-Anwendung Accelerator tabellenressourcen sind erforderlich, wenn Sie die direkte Aktivierung unterstützen möchten. Die erste Änderung kann der Benutzer zum Drücken der Taste ESC (ESC), um den direkten Bearbeitungsmodus "Abbrechen". Fügen Sie den folgenden Eintrag, um die wichtigsten Zugriffstastentabelle:  
  
|Id|Key|Typ|  
|--------|---------|----------|  
|**ID_CANCEL_EDIT_CNTR**|"VK_ESCAPE" BEZEICHNET|**VIRTKEY**|  
  
 Die zweite Änderung ist zum Erstellen einer neuen Accelerator-Tabelle, die die neue Menüressource erstellt haben, für die direkte Aktivierung entspricht. Diese Tabelle enthält Einträge für die Datei und Fenster Menüs zusätzlich zu den **"VK_ESCAPE" bezeichnet** Eintrag. Im folgende Beispiel wird die Zugriffstastentabelle, die für die direkte Aktivierung im MFC-Beispiel erstellt [CONTAINER](../visual-cpp-samples.md):  
  
|Id|Key|Typ|  
|--------|---------|----------|  
|`ID_FILE_NEW`|STRG+N|**VIRTKEY**|  
|`ID_FILE_OPEN`|STRG+O|**VIRTKEY**|  
|**ID_FILE_SAVE**|STRG+S|**VIRTKEY**|  
|**ID_FILE_PRINT**|STRG+P|**VIRTKEY**|  
|**ID_NEXT_PANE**|VK_F6|**VIRTKEY**|  
|**ID_PREV_PANE**|UMSCHALT + VK_F6|**VIRTKEY**|  
|**ID_CANCEL_EDIT_CNTR**|"VK_ESCAPE" BEZEICHNET|**VIRTKEY**|  
  
##  <a name="_core_string_table_additions_for_container_applications"></a>Zeichenfolge Tabelle Ergänzungen für Containeranwendungen  
 Die meisten der Änderungen zu Zeichenfolgentabellen für containeranwendungen entsprechen die zusätzliche Menüelemente im erwähnten [Container Menüerweiterungen](#_core_container_menu_additions). Sie geben den Text in der Statusleiste angezeigt, wenn jedes Menüelement im angezeigt wird. Beispielsweise werden hier die Zeichenfolgentabelle Einträge, die bei die der Anwendungs-Assistent generiert:  
  
|Id|Zeichenfolge|  
|--------|------------|  
|**IDP_OLE_INIT_FAILED**|Fehler bei der OLE-Initialisierung. Stellen Sie sicher, dass die OLE-Bibliotheken der richtigen Version vorliegen.|  
|**IDP_FAILED_TO_CREATE**|Fehler beim Erstellen des Objekts. Stellen Sie sicher, dass das Objekt in der systemregistrierung eingegeben wurde.|  
  
## <a name="see-also"></a>Siehe auch  
 [Menüs und Ressourcen (OLE)](../mfc/menus-and-resources-ole.md)   
 [Menüs und Ressourcen: Servererweiterungen](../mfc/menus-and-resources-server-additions.md)

