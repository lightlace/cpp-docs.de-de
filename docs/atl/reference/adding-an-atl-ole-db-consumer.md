---
title: Hinzufügen eines ATL-OLE DB-Consumers | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding ATL OLE DB consumers
- OLE DB, adding ATL OLE DB consumer to projects
- ATL OLE DB consumers
ms.assetid: f940a513-4e42-4148-b521-dd0d7dc89fa2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 95d0f16f88006c1e639b1f4a02965ad8dea6b818
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43764279"
---
# <a name="adding-an-atl-ole-db-consumer"></a>Hinzufügen eines ATL-OLE DB-Consumers

Verwenden Sie diesen Assistenten zum Hinzufügen eines ATL-OLE DB-Consumers zu einem Projekt ein. Ein ATL-OLE DB-Consumer besteht aus einer OLE DB-Accessor-Klasse und datenbindungen erforderlich, eine Datenquelle zugreifen. Das Projekt muss erstellt worden sind als eine ATL-COM-Anwendung oder als eine MFC- oder Win32-Anwendung, die ATL-Unterstützung enthält (die ATL-OLE DB-Consumer-Assistenten automatisch hinzugefügt).

**Beachten Sie** können Sie einen OLE DB-Consumer zu einem MFC-Projekt hinzufügen. Wenn Sie dies tun, fügt der ATL-OLE DB-Consumer-Assistent die erforderlichen COM-Unterstützung zu Ihrem Projekt hinzu. Dabei wird davon ausgegangen, dass Sie bei der Erstellung der MFC-Projekt ausgewählt der **ActiveX-Steuerelemente** Kontrollkästchen (in der **erweiterte Features** auf der Seite der Assistent für MFC-Anwendung), die standardmäßig aktiviert. Nach Auswahl dieser Option wird sichergestellt, dass die Anwendung ruft **CoInitialize** und **CoUninitialize**. Wenn Sie nicht ausgewählt haben **ActiveX-Steuerelemente** , wenn Sie die MFC-Projekt erstellt haben, müssen Sie rufen **CoInitialize** und **CoUninitialize** im Hauptcode.

### <a name="to-add-an-atl-ole-db-consumer-to-your-project"></a>Fügen Sie einen ATL-OLE DB-Consumer zu Ihrem Projekt

1. Klicken Sie in der Klassenansicht das Projekt ein. Klicken Sie im Kontextmenü auf **hinzufügen** , und klicken Sie dann auf **Klasse hinzufügen**.

2. Doppelklicken Sie in Visual C++-Ordner, auf die **ATL-OLE DB-Consumer** Symbol oder wählen Sie ihn, und klicken Sie auf **öffnen**.

     Der ATL-OLE DB-Consumer-Assistent wird geöffnet.

3. Definieren Sie Einstellungen wie in beschrieben [ATL-OLE DB-Consumer-Assistenten](../../atl/reference/atl-ole-db-consumer-wizard.md).

4. Klicken Sie auf **Fertig stellen** um den Assistenten zu schließen. Der neu erstellte OLE DB-Consumer-Code wird in Ihrem Projekt eingefügt.

## <a name="see-also"></a>Siehe auch

[Adding Functionality with Code Wizards (Hinzufügen neuer Funktionen mit Code-Assistenten)](../../ide/adding-functionality-with-code-wizards-cpp.md)

