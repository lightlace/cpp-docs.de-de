---
title: Erstellen des Anbieters | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/15/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, creating
ms.assetid: 2506ba8f-010d-4231-aac1-387432f7b6b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0dbdf7350eeba1a29392bafc2f099a857e212e37
ms.sourcegitcommit: db6b2ad3195e71abfb60b62f3f015f08b0a719d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2018
ms.locfileid: "49410745"
---
# <a name="creating-the-provider"></a>Erstellen des Anbieters

## <a name="to-create-an-ole-db-provider-with-the-atl-ole-db-provider-wizard"></a>OLE DB-Anbieter mit dem ATL-OLE DB-Anbieter-Assistenten erstellen

1. Mit der rechten Maustaste in des Projekts.

1. Klicken Sie im Kontextmenü auf **hinzufügen**, und klicken Sie dann auf **Klasse hinzufügen**.

1. In der **Klasse hinzufügen** Dialogfeld **installiert** > **Visual C++** > **ATL**, wählen Sie die **ATL-OLE DB-Anbieter** Symbol, und klicken Sie dann auf **öffnen**.

1. In der **ATL-OLE DB-Anbieter-Assistenten**, geben Sie einen kurzen Namen für den Anbieter in der **Kurznamen** Feld. In den folgenden Themen verwenden Sie den kurzen Namen "Meinanbieter", aber Sie können einen anderen Namen verwenden. Füllen Sie die anderen Namensfelder gemäß den von Ihnen eingegebene Name.

1. Bearbeiten Sie die anderen Namensfelder, bei Bedarf. Zusätzlich zu den-Objekt und die Dateinamen können Sie die folgenden bearbeiten:

   - **Co-Klasse**: der Name, der COM verwendet, um den Anbieter zu erstellen.

   - **ProgID**: der programmgesteuerte Bezeichner, die eine Textzeichenfolge handelt, die anstelle einer GUID verwendet werden kann.

   - **Version**: mit der Programm-ID und die Co-Klasse verwendet, um eine programmgesteuerte versionsabhängige-ID zu generieren

1. Klicken Sie auf **Fertig stellen**.

## <a name="see-also"></a>Siehe auch

[Erstellen eines OLE DB-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)
