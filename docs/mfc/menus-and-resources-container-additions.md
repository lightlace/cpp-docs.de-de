---
title: 'Menüs und Ressourcen: Containererweiterungen'
ms.date: 11/04/2016
f1_keywords:
- IDP_OLE_INIT_FAILED
- IDP_FAILED_TO_CREATE
- VK_ESCAPE
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
ms.openlocfilehash: ea4159f8eb60f43f60eacd5831ce148c81aeb572
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50546613"
---
# <a name="menus-and-resources-container-additions"></a>Menüs und Ressourcen: Containererweiterungen

Dieser Artikel beschreibt die Änderungen, die für die Menüs und andere Ressourcen in eine visuelle Bearbeitung Container-Anwendung vorgenommen werden müssen.

In containeranwendungen zwei Arten von Änderungen vorgenommen werden müssen: Änderungen an vorhandenen Ressourcen zur Unterstützung von OLE visuelle Bearbeitung und Hinzufügen von neuen Ressourcen, die für die direkte Aktivierung verwendet. Wenn Sie den Assistenten zum Erstellen Ihrer Anwendung mit Containern verwenden, werden diese Schritte für Sie ausgeführt werden, aber einige Anpassungen erforderlich sein.

Wenn Sie nicht der Anwendungs-Assistent verwenden, empfiehlt es sich um OCLIENT anzuzeigen. RC-Version das Ressourcenskript für die OCLIENT-beispielanwendung, um festzustellen, wie diese Änderungen implementiert werden. Finden Sie im MFC-OLE-Beispiel [OCLIENT](../visual-cpp-samples.md).

In diesem Artikel behandelten Themen umfassen:

- [Container-Menüerweiterungen](#_core_container_menu_additions)

- [Accelerator-Tabelle hinzufügen](#_core_container_application_accelerator_table_additions)

- [Erweiterungen für Zeichenfolge-Tabelle](#_core_string_table_additions_for_container_applications)

##  <a name="_core_container_menu_additions"></a> Container-Menüerweiterungen

Sie müssen die folgenden Elemente hinzufügen, um das Menü "Bearbeiten":

|Element|Zweck|
|----------|-------------|
|**Neues Objekt einfügen**|Öffnet das Dialogfeld OLE Objekt einfügen, um ein verknüpftes oder eingebettetes Element in das Dokument einzufügen.|
|**Link einfügen**|Fügt einen Link zum Element in der Zwischenablage in das Dokument an.|
|**OLE-Verb**|Ruft das ausgewählte Element primäres Verb. Der Text des dieses Menüelement ändert sich das primäre Verb des ausgewählten Elements entsprechen.|
|**Links**|Öffnet das Dialogfeld OLE Verknüpfungen bearbeiten, um vorhandene verknüpfte Elemente zu ändern.|

Zusätzlich zu den Änderungen, die in diesem Artikel aufgeführt wird muss die Quelldatei AFXOLECL enthalten. RC-Version für die Microsoft Foundation Class Library-Implementierung erforderlich ist. Neues Objekt einfügen, ist das einzige erforderliche Menü hinzufügen. Andere Elemente hinzugefügt werden können, aber die hier aufgeführten sind die häufigsten.

Wenn Sie direkte Aktivierung von enthaltenen Elementen unterstützen möchten, müssen Sie ein neues Menü für Ihre containeranwendung erstellen. Dieses Menü besteht aus den gleichen Menü "Datei" und Fenster-Popup-Menüs verwendet wird, wenn Dateien geöffnet sind, aber sie zwei Trennzeichen dazwischen eingefügt hat. Diese Trennzeichen werden verwendet, um anzugeben, in dem das Element für Server (Komponente) (Anwendung) Menüs bei direkt aktiviert zu platzieren sollten. Weitere Informationen zu diesem Verfahren das Zusammenführen von Menüs, finden Sie unter [Menüs und Ressourcen: Menüs schachteln](../mfc/menus-and-resources-menu-merging.md).

##  <a name="_core_container_application_accelerator_table_additions"></a> Anwendung Accelerator Tabelle Containererweiterungen

Kleine Änderungen an einer containeranwendung Accelerator tabellenressourcen sind erforderlich, wenn Sie direkte Aktivierung unterstützen. Die erste Änderung kann der Benutzer die ESC-Taste (ESC), um den direkten Bearbeitungsmodus abzubrechen, drücken Sie EINGABETASTE. Fügen Sie den folgenden Eintrag zu den wichtigsten Zugriffstastentabelle:

|Id|Key|Typ|
|--------|---------|----------|
|ID_CANCEL_EDIT_CNTR|"VK_ESCAPE"|**VIRTKEY**|

Die zweite Änderung ist zum Erstellen einer neuen Accelerator-Tabelle, die die neue Menüressource erstellt haben, für die direkte Aktivierung entspricht. Diese Tabelle enthält Einträge für die Datei und Fenster Menüs neben dem Eintrag "VK_ESCAPE". Im folgende Beispiel wird die Zugriffstastentabelle, die für die direkte Aktivierung im MFC-Beispiel erstellten [CONTAINER](../visual-cpp-samples.md):

|Id|Key|Typ|
|--------|---------|----------|
|ID_FILE_NEW|STRG+N|**VIRTKEY**|
|ID_FILE_OPEN|STRG+O|**VIRTKEY**|
|ID_FILE_SAVE|STRG+S|**VIRTKEY**|
|ID_FILE_PRINT|STRG+P|**VIRTKEY**|
|ID_NEXT_PANE|VK_F6|**VIRTKEY**|
|ID_PREV_PANE|UMSCHALT + VK_F6|**VIRTKEY**|
|ID_CANCEL_EDIT_CNTR|"VK_ESCAPE"|**VIRTKEY**|

##  <a name="_core_string_table_additions_for_container_applications"></a> Zeichenfolge Tabelle Ergänzungen für Containeranwendungen

Die meisten Änderungen an den Zeichenfolgentabellen für containeranwendungen entsprechen, die zusätzliche Menüelemente in erwähnt [Container Menüerweiterungen](#_core_container_menu_additions). Sie geben den Text in der Statusleiste angezeigt wird, wenn jedes Menüelement im angezeigt wird. Hier sind die Zeichenfolgentabelle Einträge, die die Anwendungs-Assistent erstellt, beispielsweise:

|Id|Zeichenfolge|
|--------|------------|
|IDP_OLE_INIT_FAILED|Fehler bei der OLE-Initialisierung. Stellen Sie sicher, dass die OLE-Bibliotheken der richtigen Version vorliegen.|
|IDP_FAILED_TO_CREATE|Fehler beim Erstellen des Objekts. Stellen Sie sicher, dass das Objekt in der systemregistrierung eingetragen ist.|

## <a name="see-also"></a>Siehe auch

[Menüs und Ressourcen (OLE)](../mfc/menus-and-resources-ole.md)<br/>
[Menüs und Ressourcen: Servererweiterungen](../mfc/menus-and-resources-server-additions.md)

