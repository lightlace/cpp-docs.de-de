---
title: 'Menüs und Ressourcen: Servererweiterungen'
ms.date: 11/04/2016
f1_keywords:
- IDP_OLE_INIT_FAILED
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
ms.openlocfilehash: 85c7b6059a868e93c6c6a7ebbd7b08dac3233612
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58767198"
---
# <a name="menus-and-resources-server-additions"></a>Menüs und Ressourcen: Servererweiterungen

Dieser Artikel beschreibt die Änderungen, die mit den Menüs und anderen Ressourcen in einer visual bearbeiten (Komponente) Serveranwendung vorgenommen werden müssen. Eine Serveranwendung erfordert viele Erweiterungen für die Menüstruktur und andere Ressourcen aus, da es in einem von drei Modi gestartet werden kann: allein stehen, embedded oder vorhanden. Siehe die [Menüs und Ressourcen (OLE)](../mfc/menus-and-resources-ole.md) beschrieben, gibt es höchstens vier Sätze von Menüs. Alle vier sind für eine MDI-voll-Server-Anwendung verwendet werden, während nur drei für ein Miniserver verwendet werden. Der Anwendungs-Assistent wird das Menülayout für den Typ des Servers erforderlich gewünschten erstellen. Einige Anpassungen kann erforderlich sein.

Wenn Sie nicht der Anwendungs-Assistent verwenden, empfiehlt es sich um HIERSVR anzuzeigen. RC-Version das Ressourcenskript für die MFC-beispielanwendung [HIERSVR](../overview/visual-cpp-samples.md), um anzuzeigen, wie diese Änderungen implementiert werden.

In diesem Artikel behandelten Themen umfassen:

- [Menü-Servererweiterungen](#_core_server_menu_additions)

- [Accelerator-Tabelle hinzufügen](#_core_server_application_accelerator_table_additions)

- [Erweiterungen für Zeichenfolge-Tabelle](../mfc/menus-and-resources-container-additions.md)

- [Miniserver-Erweiterungen](#_core_mini.2d.server_additions)

##  <a name="_core_server_menu_additions"></a> Menü-Servererweiterungen

Serveranwendungen (Komponente) müssen Menüressourcen hinzugefügt, um OLE visuelle Bearbeitung unterstützen. Die Menüs verwendet, wenn die Anwendung im eigenständigen Modus ausgeführt wird, müssen nicht geändert werden, aber Sie müssen zwei neue Menüressourcen vor dem Erstellen der Anwendung hinzufügen: eines zur Unterstützung der direkten Aktivierung und eine zum unterstützen des Servers vollständig geöffnet wird. Beide Menüressourcen werden von vollständigen und Miniserver Anwendungen verwendet.

- Zur Unterstützung der direkten Aktivierung müssen Sie eine Menüressource erstellen, die die Menüressource verwendet, wenn die Ausführung im eigenständigen Modus sehr ähnlich ist. Der Unterschied in diesem Menü ist, dass die Datei und Fenster-Elemente (und alle anderen Menüelemente, die die Anwendung und nicht die Daten verarbeiten) fehlen. Die Container-Anwendung stellt diesen Menüelementen bereit. Weitere Informationen zu, und ein Beispiel für dieses Verfahren das Zusammenführen von Menüs, finden Sie im Artikel [Menüs und Ressourcen: Das Zusammenführen von Menüs](../mfc/menus-and-resources-menu-merging.md).

- Um vollständig open Aktivierung zu unterstützen, müssen Sie nahezu identisch mit der verwendeten Ressource eine Ausführung im eigenständigen Modus Menüressource erstellen. Auf diese Menüressource im die einzige Änderung ist, dass einige Elemente-systemintegritätsprüfung werden entsprechend die Tatsache, die der Server ausgeführt wird, auf ein Element in einem Verbunddokument eingebettet.

Zusätzlich zu den Änderungen, die in diesem Artikel aufgeführt wird muss Ihre Ressourcendatei AFXOLESV enthalten. RC-Version für die Microsoft Foundation Class Library-Implementierung erforderlich ist. Diese Datei befindet sich im Unterverzeichnis MFC\Include.

##  <a name="_core_server_application_accelerator_table_additions"></a> Anwendung Accelerator Tabelle Servererweiterungen

Zwei neue Zugriffstaste tabellenressourcen müssen für Server-Anwendungen hinzugefügt werden; Sie entsprechen direkt an die neuen Menüressourcen, die zuvor beschrieben. Die erste Zugriffstastentabelle wird verwendet, wenn die Serveranwendung direkt aktiviert ist. Es besteht aus allen Einträgen in der Ansicht Zugriffstastentabelle außer denen Menüs in die Datei und gebunden.

Die zweite Tabelle ist praktisch eine exakte Kopie des Zugriffstastentabelle der Ansicht. Alle Unterschiede parallele Änderungen in das Menü mit der Option vollständig öffnen, die im genannten [Server Menüerweiterungen](#_core_server_menu_additions).

Ein Beispiel dieser Accelerator Tabelle Änderungen vergleichen Sie die Zugriffstastentabellen IDR_HIERSVRTYPE_SRVR_IP und IDR_HIERSVRTYPE_SRVR_EMB mit IDR_MAINFRAME in die HIERSVR. RC-Datei in den MFC-OLE-Beispiel enthaltenen [HIERSVR](../overview/visual-cpp-samples.md). Die Datei und Fenster-Accelerators fehlen in der Tabelle des direktes und genaue Kopien von ihnen in der eingebettete Tabelle.

##  <a name="_core_string_table_additions_for_server_applications"></a> Zeichenfolge Tabelle Ergänzungen für Serveranwendungen

Die Tabelle außerdem nur eine Zeichenfolge ist in einer Serveranwendung erforderlich – eine Zeichenfolge, um anzugeben, dass der OLE-Initialisierung fehlgeschlagen ist. Als Beispiel ist hier der Zeichenfolgentabelle Eintrag, den der Anwendungs-Assistent generiert:

|ID|Zeichenfolge|
|--------|------------|
|IDP_OLE_INIT_FAILED|Fehler bei der OLE-Initialisierung. Stellen Sie sicher, dass die OLE-Bibliotheken der richtigen Version vorliegen.|

##  <a name="_core_mini.2d.server_additions"></a> Miniserver-Erweiterungen

Die gleichen Ergänzungen gelten für Miniserver als die oben aufgeführten für voll-Server. Da ein Miniserver im eigenständigen Modus ausgeführt werden kann, ist die Hauptmenü deutlich kleiner. Im Hauptmenü auf, die vom Anwendungs-Assistenten erstellt wurde, nur ein Dateimenü enthält nur die Elemente beenden und zum. Eingebettete und in-Place-Menüs und Zugriffstasten für Miniserver sind identisch mit denen für voll-Server.

## <a name="see-also"></a>Siehe auch

[Menüs und Ressourcen (OLE)](../mfc/menus-and-resources-ole.md)<br/>
[Menüs und Ressourcen: Zusammenführen von Menüs](../mfc/menus-and-resources-menu-merging.md)
