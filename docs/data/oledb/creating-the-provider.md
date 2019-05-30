---
title: Erstellen des Anbieters
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB providers, creating
ms.assetid: 2506ba8f-010d-4231-aac1-387432f7b6b9
ms.openlocfilehash: 7a8b4caf85ff7d0310c97cb953739796cca21c43
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65707580"
---
# <a name="creating-the-provider"></a>Erstellen des Anbieters

::: moniker range="vs-2019"

Der ATL-OLE DB-Anbieter-Assistent ist in Visual Studio 2019 und höher nicht verfügbar.

::: moniker-end

::: moniker range="<=vs-2017"

## <a name="to-create-an-ole-db-provider-with-the-atl-ole-db-provider-wizard"></a>So erstellen Sie mit dem ATL-OLE DB-Anbieter-Assistenten einen OLE DB-Anbieter

1. Klicken Sie mit der rechten Maustaste auf das Projekt.

1. Klicken Sie im Kontextmenü auf **Hinzufügen**, und klicken Sie danach auf **Klasse hinzufügen**.

1. Wählen Sie im Dialogfeld **Klasse hinzufügen** unter **Installiert** > **Visual C++** > **ATL** das Symbol **ATL-OLE DB-Anbieter** aus, und klicken Sie dann auf **Öffnen**.

1. Geben Sie im **ATL-OLE DB-Anbieter-Assistenten** im Feld **Kurzname** einen Kurznamen für Ihren Anbieter ein. In den folgenden Themen wird der Kurzname *Custom* verwendet, aber Sie können einen anderen Namen verwenden. Die weiteren Namensfelder werden basierend auf dem eingegebenen Namen automatisch aufgefüllt.

1. Bearbeiten Sie bei Bedarf die weiteren Namensfelder. Zusätzlich zu den Objekt- und Dateinamen können Sie folgende Felder bearbeiten:

   - **Co-Klasse**: Der von der COM-Komponente verwendete Name zum Erstellen des Anbieters.

   - **ProgID**: Dieser programmgesteuerte Bezeichner ist eine Textzeichenfolge, die anstelle einer GUID verwendet werden kann.

   - **Version**: Wird mit der ProgID und der Co-Klasse verwendet, um eine versionsabhängige programmgesteuerte ID zu generieren.

1. Klicken Sie auf **Fertig stellen**.

::: moniker-end

## <a name="see-also"></a>Siehe auch

[Erstellen eines OLE DB-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)
