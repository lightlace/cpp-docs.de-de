---
title: Hinzufügen eines ATL-OLE DB-Consumers
ms.date: 05/09/2019
helpviewer_keywords:
- ATL OLE DB consumers
ms.assetid: f940a513-4e42-4148-b521-dd0d7dc89fa2
ms.openlocfilehash: 1e384a283a2a149faa5b8d6e0817eac3cacfeff9
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65706921"
---
# <a name="adding-an-atl-ole-db-consumer"></a>Hinzufügen eines ATL-OLE DB-Consumers

::: moniker range="vs-2019"

Der ATL-OLE DB-Consumer-Assistent ist in Visual Studio 2019 und höher nicht verfügbar. Sie können diese Funktionalität weiterhin manuell hinzufügen. Weitere Informationen finden Sie unter [Erstellen eines Consumers ohne Assistent](../../data/oledb/creating-a-consumer-without-using-a-wizard.md).

::: moniker-end

::: moniker range="<=vs-2017"

Verwenden Sie diesen Assistenten, um einem Projekt einen ATL-OLE DB-Consumer hinzuzufügen. Ein ATL-OLE DB-Consumer besteht aus einer OLE DB-Zugriffsmethodenklasse und den Datenbindungen, die für den Zugriff auf eine Datenquelle erforderlich sind. Das Projekt muss als ATL-COM-Anwendung oder als MFC- oder Win32-Anwendung erstellt worden sein, die ATL-Unterstützung enthält (die vom ATL-OLE DB-Consumer-Assistenten automatisch hinzugefügt wird).

> [!NOTE]
> Sie können einen OLE DB-Consumer zu einem MFC-Projekt hinzufügen. In diesem Fall fügt der ATL-OLE DB-Consumer-Assistent Ihrem Projekt die erforderliche COM-Unterstützung hinzu. Dabei wird vorausgesetzt, dass Sie beim Erstellen des MFC-Projekts das Kontrollkästchen **ActiveX-Steuerelemente** (auf der Seite **Erweiterte Features** des MFC-Projektanwendungs-Assistenten) ausgewählt haben, das standardmäßig aktiviert ist. Durch Auswahl diese Option ist sichergestellt, dass die Anwendung `CoInitialize` und `CoUninitialize` aufruft. Wenn Sie beim Erstellen des MFC-Projekts das Kontrollkästchen **ActiveX-Steuerelemente** nicht ausgewählt haben, müssen Sie `CoInitialize` und `CoUninitialize` im Hauptcode aufrufen.

## <a name="to-add-an-atl-ole-db-consumer-to-your-project"></a>So fügen Sie einen ATL-OLE DB-Consumer zum Projekt hinzu

1. Klicken Sie in der **Klassenansicht** mit der rechten Maustaste auf das Projekt. Klicken Sie im Kontextmenü auf **Hinzufügen**, und klicken Sie danach auf **Klasse hinzufügen**.

1. Doppelklicken Sie im Ordner „Visual C++“ auf das Symbol **ATL-OLE DB-Consumer**, oder wählen Sie es aus. Klicken Sie dann auf **Öffnen**.

   Der ATL-OLE DB-Consumer-Assistent wird geöffnet.

1. Definieren Sie die Einstellungen wie in [ATL-OLE DB-Consumer-Assistent](../../atl/reference/atl-ole-db-consumer-wizard.md) beschrieben.

1. Klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen. Der neu erstellte OLE DB-Consumercode wird in Ihr Projekt eingefügt.

::: moniker-end

## <a name="see-also"></a>Siehe auch

[Hinzufügen neuer Funktionen mit Code-Assistenten](../../ide/adding-functionality-with-code-wizards-cpp.md)
