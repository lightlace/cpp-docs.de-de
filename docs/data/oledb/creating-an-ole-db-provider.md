---
title: Erstellen eines OLE DB-Anbieters | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/13/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, creating
- OLE DB provider templates, creating providers
ms.assetid: f73017c3-c89f-41a6-a306-ea992cf6092c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7c3d94bec2638901f542dfa7c412da0de9a60942
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50078297"
---
# <a name="creating-an-ole-db-provider"></a>Erstellen eines OLE DB-Anbieters

Die empfohlene Methode zum Erstellen eines OLE DB-Anbieters ist die Verwendung des Assistenten zum Erstellen eines ATL-COM-Projekts und eines Anbieters, und klicken Sie dann ändern Sie die Dateien, die mithilfe der OLE DB-Vorlagen. Während Sie Ihren Anbieter anpassen, können nicht benötigte Eigenschaften auskommentieren und optionale Schnittstellen hinzufügen.

Die grundlegenden Schritte werden im Folgenden beschrieben:

1. Verwenden der **ATL-Projektassistenten** die grundlegenden Projektdateien erstellen und die **ATL-OLE DB-Anbieter-Assistent** zum Erstellen des Anbieters (Wählen Sie **ATL-OLE DB-Anbieter** aus der **Installiert** > **Visual C++** > **ATL** Ordner **neues Element hinzufügen**).

   > [!NOTE]
   > Das Projekt muss vor dem Hinzufügen von MFC-Unterstützung enthält eine **ATL-OLE DB-Anbieter**.

1. Ändern Sie den Code in die `Execute` -Methode in der [CCustomRowset(CustomRS.h)](cmyproviderrowset-myproviderrs-h.md). Ein Beispiel finden Sie unter [Einlesen von Zeichenfolgen in den OLE DB-Anbieter](../../data/oledb/reading-strings-into-the-ole-db-provider.md).

1. Bearbeiten Sie die Eigenschaft zugeordnet wird, im [CustomDS.h](cmyprovidersource-myproviderds-h.md), [CustomSess.h](cmyprovidersession-myprovidersess-h.md), und [CustomRS.h](cmyproviderrowset-myproviderrs-h.md). Der Assistent erstellt die eigenschaftenzuordnungen, die alle Eigenschaften enthalten, die ein Anbieter implementieren kann. Durchlaufen Sie die eigenschaftenzuordnungen, und entfernen oder kommentieren Sie die Eigenschaften, die Ihr Anbieter nicht unterstützen muss.

1. Aktualisieren von Makro, das im befinden [CCustomRowset(CustomRS.h)](cmyproviderrowset-myproviderrs-h.md). Ein Beispiel finden Sie unter [Speichern von Zeichenfolgen im OLE DB-Anbieter](../../data/oledb/storing-strings-in-the-ole-db-provider.md).

1. Wenn Sie zum Testen des Anbieters bereit sind, können Sie es testen, indem Sie versuchen, die der Anbieter in einer Anbieterenumeration finden. Beispiele für Testcode, die einen Anbieter in einer Enumeration sucht, finden Sie unter den [CATDB](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/catdb) und [DBVIEWER](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/dbviewer) Beispiele oder nur das Beispiel in [Implementieren eines einfachen Consumers](../../data/oledb/implementing-a-simple-consumer.md).

1. Fügen Sie alle zusätzlichen Schnittstellen gewünschten hinzu. Ein Beispiel finden Sie unter [Erweitern des einfachen schreibgeschützten Anbieters](../../data/oledb/enhancing-the-simple-read-only-provider.md).

   > [!NOTE]
   > Die Assistenten generieren standardmäßig Code, der OLE DB-Ebene 0 kompatibel ist. Um sicherzustellen, dass Ihre Anwendung auf Ebene 0 kompatibel bleiben, führen Sie keine der vom Assistenten generierten Schnittstellen aus dem Code entfernt.

## <a name="see-also"></a>Siehe auch

[CatDB-Beispiel: Schema Datenquellenbrowser](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/catdb)<br/>
[Beispiel für dieses Beispiel: Datenbankbrowser](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/dbviewer)
