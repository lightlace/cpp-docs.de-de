---
title: Erstellen des Anbieters
ms.date: 10/15/2018
helpviewer_keywords:
- OLE DB providers, creating
ms.assetid: 2506ba8f-010d-4231-aac1-387432f7b6b9
ms.openlocfilehash: 6258b5247e4d9d027e0f03bc133dff1a059665bd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62361857"
---
# <a name="creating-the-provider"></a>Erstellen des Anbieters

## <a name="to-create-an-ole-db-provider-with-the-atl-ole-db-provider-wizard"></a>OLE DB-Anbieter mit dem ATL-OLE DB-Anbieter-Assistenten erstellen

1. Klicken Sie mit der rechten Maustaste auf das Projekt.

1. Klicken Sie im Kontextmenü auf **hinzufügen**, und klicken Sie dann auf **Klasse hinzufügen**.

1. In der **Klasse hinzufügen** Dialogfeld **installiert** > **Visual C++** > **ATL**, wählen Sie die **ATL-OLE DB-Anbieter** Symbol, und klicken Sie dann auf **öffnen**.

1. In der **ATL-OLE DB-Anbieter-Assistenten**, geben Sie einen kurzen Namen für den Anbieter in der **Kurznamen** Feld. In den folgenden Themen verwenden Sie den kurzen Namen *benutzerdefinierte*, aber Sie können einen anderen Namen verwenden. Füllen Sie die anderen Namensfelder gemäß den von Ihnen eingegebene Name.

1. Bearbeiten Sie die anderen Namensfelder, bei Bedarf. Zusätzlich zu den-Objekt und die Dateinamen können Sie die folgenden bearbeiten:

   - **Co-Klasse**: Der Name, die COM verwendet, um den Anbieter zu erstellen.

   - **ProgID**: Der programmgesteuerte Bezeichner, der eine Textzeichenfolge handelt, die anstelle einer GUID verwendet werden kann.

   - **Version**: Mit der Programm-ID und die Co-Klasse verwendet, um eine programmgesteuerte versionsabhängige-ID zu generieren

1. Klicken Sie auf **Fertig stellen**.

## <a name="see-also"></a>Siehe auch

[Erstellen eines OLE DB-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)
