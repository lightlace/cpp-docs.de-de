---
title: Erstellen des Anbieters | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 1063b3418df0c9dd45848ea71cdd7717c2dd1427
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2018
ms.locfileid: "48859587"
---
# <a name="creating-the-provider"></a>Erstellen des Anbieters

#### <a name="to-create-an-ole-db-provider-with-the-atl-ole-db-provider-wizard"></a>OLE DB-Anbieter mit dem ATL-OLE DB-Anbieter-Assistenten erstellen

1. Mit der rechten Maustaste in des Projekts.

1. Klicken Sie im Kontextmenü auf **hinzufügen**, und klicken Sie dann auf **Klasse hinzufügen**.

1. In der **Klasse hinzufügen** wählen Sie im Dialogfeld die **ATL-OLE DB-Anbieter** Symbol, und klicken Sie dann auf **öffnen**.

1. Geben Sie in der ATL-OLE DB-Anbieter-Assistenten einen kurzen Namen für den Anbieter in der **Kurznamen** Feld. In den folgenden Themen verwenden Sie den kurzen Namen "Meinanbieter", aber Sie können einen anderen Namen verwenden. Füllen Sie die anderen Namensfelder gemäß den von Ihnen eingegebene Name.

1. Bearbeiten Sie die anderen Namensfelder, bei Bedarf. Zusätzlich zu den-Objekt und die Dateinamen können Sie die folgenden bearbeiten:

   - **Co-Klasse**: der Name, der COM verwendet, um den Anbieter zu erstellen.

   - **ProgID**: der programmgesteuerte Bezeichner, die eine Textzeichenfolge handelt, die anstelle einer GUID verwendet werden kann.

   - **Version**: mit der Programm-ID und die Co-Klasse verwendet, um eine programmgesteuerte versionsabhängige-ID zu generieren

1. Klicken Sie auf **Fertig stellen**.

## <a name="see-also"></a>Siehe auch

[Erstellen eines OLE DB-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)
