---
title: Hinzufügen eines ATL-OLE DB-Consumers
ms.date: 11/04/2016
helpviewer_keywords:
- ATL projects, adding ATL OLE DB consumers
- OLE DB, adding ATL OLE DB consumer to projects
- ATL OLE DB consumers
ms.assetid: f940a513-4e42-4148-b521-dd0d7dc89fa2
ms.openlocfilehash: d93bf715f8fd8a03c75b1d1bf2e44f12c1d1b9c0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62261376"
---
# <a name="adding-an-atl-ole-db-consumer"></a>Hinzufügen eines ATL-OLE DB-Consumers

Verwenden Sie diesen Assistenten zum Hinzufügen eines ATL-OLE DB-Consumers zu einem Projekt ein. Ein ATL-OLE DB-Consumer besteht aus einer OLE DB-Accessor-Klasse und datenbindungen erforderlich, eine Datenquelle zugreifen. Das Projekt muss erstellt worden sind als eine ATL-COM-Anwendung oder als eine MFC- oder Win32-Anwendung, die ATL-Unterstützung enthält (die ATL-OLE DB-Consumer-Assistenten automatisch hinzugefügt).

> [!NOTE]
> Sie können einen OLE DB-Consumer zu einem MFC-Projekt hinzufügen. Wenn Sie dies tun, fügt der ATL-OLE DB-Consumer-Assistent die erforderlichen COM-Unterstützung zu Ihrem Projekt hinzu. Dabei wird davon ausgegangen, dass Sie bei der Erstellung der MFC-Projekt ausgewählt der **ActiveX-Steuerelemente** Kontrollkästchen (in der **erweiterte Features** auf der Seite der Assistent für MFC-Anwendung), die standardmäßig aktiviert. Nach Auswahl dieser Option wird sichergestellt, dass die Anwendung ruft `CoInitialize` und `CoUninitialize`. Wenn Sie nicht ausgewählt haben **ActiveX-Steuerelemente** , wenn Sie die MFC-Projekt erstellt haben, müssen Sie rufen `CoInitialize` und `CoUninitialize` im Hauptcode.

## <a name="to-add-an-atl-ole-db-consumer-to-your-project"></a>Fügen Sie einen ATL-OLE DB-Consumer zu Ihrem Projekt

1. In **Klassenansicht**, mit der rechten Maustaste in des Projekts. Klicken Sie im Kontextmenü auf **hinzufügen** , und klicken Sie dann auf **Klasse hinzufügen**.

1. Doppelklicken Sie in Visual C++-Ordner, auf die **ATL-OLE DB-Consumer** Symbol oder wählen Sie ihn, und klicken Sie auf **öffnen**.

   Der ATL-OLE DB-Consumer-Assistent wird geöffnet.

1. Definieren Sie Einstellungen wie in beschrieben [ATL-OLE DB-Consumer-Assistenten](../../atl/reference/atl-ole-db-consumer-wizard.md).

1. Klicken Sie auf **Fertig stellen** um den Assistenten zu schließen. Der neu erstellte OLE DB-Consumer-Code wird in Ihrem Projekt eingefügt.

## <a name="see-also"></a>Siehe auch

[Adding Functionality with Code Wizards (Hinzufügen neuer Funktionen mit Code-Assistenten)](../../ide/adding-functionality-with-code-wizards-cpp.md)
