---
title: 'Menüs und Ressourcen: Servererweiterungen | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- IDP_OLE_INIT_FAILED
dev_langs:
- C++
helpviewer_keywords:
- OLE visual editing servers [MFC]
- accelerator tables [MFC], server applications
- visual editing [MFC], application menus and resources
- server applications [MFC], accelerator table
- string tables [MFC], visual editing applications
- servers [MFC], menu additions
- resources [MFC], server applications
- OLE server applications [MFC], menus and resources
- string editing [MFC], visual editing applications
- IDP_OLE_INIT_FAILED macro [MFC]
- server applications [MFC], OLE menus and resources
- OLE initialization failure [MFC]
ms.assetid: 56ce9e8d-8f41-4db8-8dee-e8b0702d057c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cbcedd8cf217c993511bdb84a89294d7e98d6bab
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930201"
---
# <a name="menus-and-resources-server-additions"></a>Menüs und Ressourcen: Servererweiterungen
Dieser Artikel beschreibt die Änderungen, die mit den Menüs und anderen Ressourcen in ein visual bearbeitungsanwendung-Server (Komponente) vorgenommen werden müssen. Eine Serveranwendung muss viele Ergänzungen für die Menüstruktur und andere Ressourcen, da er in einem von drei Modi gestartet werden kann: Standalone, eingebettet sind, oder vorhanden. Wie in beschrieben die [Menüs und Ressourcen (OLE)](../mfc/menus-and-resources-ole.md) Artikel, es sind maximal vier Sätze von Menüs. Alle vier werden für eine MDI-Vollserver-Anwendung verwendet, während nur drei für ein Miniserver verwendet werden. Der Anwendungs-Assistent wird das Layout im Menü für den Typ des Servers erforderlich erstellt werden sollen. Einige Anpassung kann notwendig sein.  
  
 Wenn Sie den Anwendungsassistenten nicht verwenden, empfiehlt es sich um HIERSVR betrachten. RC, das Ressourcenskript für die MFC-beispielanwendung [HIERSVR](../visual-cpp-samples.md), um festzustellen, wie diese Änderungen implementiert werden.  
  
 In diesem Artikel behandelten Themen werden behandelt:  
  
-   [Server-Menüerweiterungen](#_core_server_menu_additions)  
  
-   [Accelerator Tabelle hinzufügen](#_core_server_application_accelerator_table_additions)  
  
-   [Zeichenfolge Tabelle hinzufügen](../mfc/menus-and-resources-container-additions.md)  
  
-   [Miniserver Ergänzungen](#_core_mini.2d.server_additions)  
  
##  <a name="_core_server_menu_additions"></a> Server-Menüerweiterungen  
 Serveranwendungen (Komponente) benötigen Menüressourcen hinzugefügt, um OLE visuelle Bearbeitung unterstützen. Die Menüs verwendet, wenn die Anwendung, im eigenständigen Modus ausgeführt wird müssen nicht geändert werden, jedoch müssen Sie zwei neue Menüressourcen vor dem Erstellen der Anwendung hinzufügen: eines zur Unterstützung von direkte Aktivierung und eins, um den Server vollständig geöffnet wird unterstützt. Beide Menüressourcen werden von vollständigen und Miniserver Anwendungen verwendet.  
  
-   Zur Unterstützung der direkten Aktivierung müssen Sie eine Menüressource erstellen, die die Menüressource verwendet, wenn die Ausführung im eigenständigen Modus sehr ähnlich sind. Der Unterschied in diesem Menü sind, dass die Datei und Fenster-Elemente (und alle anderen Menüelemente, die mit der Anwendung und nicht die Daten zu verarbeiten) fehlen. Diese Menüelemente bereitstellt Steuerelementcontainer-Anwendung. Weitere Informationen zu, und ein Beispiel für dieses Verfahren das Zusammenführen von Menüs, finden Sie im Artikel [Menüs und Ressourcen: Menüs schachteln](../mfc/menus-and-resources-menu-merging.md).  
  
-   Um vollständig offen Aktivierung zu unterstützen, müssen Sie fast identisch mit der Menüressource verwendet eine bei der Ausführung im eigenständigen Modus Menüressource erstellen. Die einzige Änderung an dieser Menüressource ist, dass einige Elemente neu formulierte werden entsprechend der Tatsache, die dass die der Server ausgeführt wird, auf ein Element in einem zusammengesetzten Dokument eingebettet.  
  
 Zusätzlich zu den Änderungen, die in diesem Artikel aufgeführt wird muss Ihre Ressourcendatei AFXOLESV enthalten. RC, die für die Microsoft Foundation Class Library-Implementierung erforderlich ist. Diese Datei befindet sich im Unterverzeichnis MFC\Include.  
  
##  <a name="_core_server_application_accelerator_table_additions"></a> Anwendung Accelerator Tabelle Servererweiterungen  
 Zwei neue Zugriffstaste tabellenressourcen müssen Server-Anwendungen hinzugefügt werden; Sie entsprechen direkt den neuen Menüressourcen, die zuvor beschriebenen. Die erste Zugriffstastentabelle wird verwendet, wenn die Serveranwendung direkt aktiviert ist. Er besteht aus alle Einträge in der Ansicht Zugriffstastentabelle außer denen Menüs in die Datei und gebunden.  
  
 Die zweite Tabelle ist nahezu eine genaue Kopie der Ansicht Zugriffstastentabelle. Alle Unterschiede parallele Änderungen in der vollständig Öffnen des Menüs in erwähnt [Server Menüerweiterungen](#_core_server_menu_additions).  
  
 Ein Beispiel für diese Zugriffstaste tabellenänderungen vergleichen Sie die Zugriffstastentabellen IDR_HIERSVRTYPE_SRVR_IP und IDR_HIERSVRTYPE_SRVR_EMB mit IDR_MAINFRAME in die HIERSVR. RC-Datei in der MFC-OLE-Beispiel enthaltenen [HIERSVR](../visual-cpp-samples.md). Die Datei und Fenster-Zugriffstasten fehlen in der Tabelle für die direkte und genaue Kopien der Berichtsmomentaufnahmen werden in der eingebettete Tabelle.  
  
##  <a name="_core_string_table_additions_for_server_applications"></a> Zeichenfolge Tabelle Ergänzungen für Serveranwendungen  
 Die Tabelle außerdem nur eine Zeichenfolge ist erforderlich, in einer Serveranwendung – eine Zeichenfolge, um anzugeben, dass der OLE-Initialisierung fehlgeschlagen ist. Beispielsweise ist hier der Zeichenfolgentabelle Eintrag, den die Anwendungs-Assistent erstellt ein:  
  
|Id|Zeichenfolge|  
|--------|------------|  
|IDP_OLE_INIT_FAILED|Fehler bei der OLE-Initialisierung. Stellen Sie sicher, dass die OLE-Bibliotheken der richtigen Version vorliegen.|  
  
##  <a name="_core_mini.2d.server_additions"></a> Miniserver Ergänzungen  
 Die gleichen Ergänzungen gelten für Miniserver als die oben aufgeführten für vollständige-Server. Weil ein Miniserver im eigenständigen Modus ausgeführt werden kann, ist dessen Hauptmenü deutlich kleiner. Das Hauptmenü vom Anwendungs-Assistenten erstellt wurde, nur eine im Dateimenü, enthält nur die Elemente beenden und zu. Eingebettete und direkte Menüs und Zugriffstasten für Miniserver sind identisch für vollständige-Server.  
  
## <a name="see-also"></a>Siehe auch  
 [Menüs und Ressourcen (OLE)](../mfc/menus-and-resources-ole.md)   
 [Menüs und Ressourcen: Menüs schachteln](../mfc/menus-and-resources-menu-merging.md)

