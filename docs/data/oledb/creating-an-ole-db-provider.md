---
title: Erstellen eines OLE DB-Anbieters | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 16d78d590201ea637dd6153edb40a1c6d89a82c0
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43210340"
---
# <a name="creating-an-ole-db-provider"></a>Erstellen eines OLE DB-Anbieters
Die empfohlene Methode zum Erstellen eines OLE DB-Anbieters ist die Verwendung des Assistenten zum Erstellen eines ATL-COM-Projekts und eines Anbieters, und klicken Sie dann ändern Sie die Dateien, die mithilfe der OLE DB-Vorlagen. Während Sie Ihren Anbieter anpassen, können nicht benötigte Eigenschaften auskommentieren und optionale Schnittstellen hinzufügen.  
  
 Die grundlegenden Schritte werden im Folgenden beschrieben:  
  
1.  ATL-Projektassistenten verwenden, um die grundlegende Projektdateien und die ATL-OLE DB-Anbieter-Assistenten aus, zum Erstellen des Anbieters zu erstellen (Wählen Sie **ATL-OLE DB-Anbieter** aus dem Visual C++-Ordner im **Klasse hinzufügen**).  
  
2.  Ändern Sie den Code in die `Execute` -Methode in der Datei CMyProviderRS.h. Ein Beispiel finden Sie unter [Einlesen von Zeichenfolgen in den OLE DB-Anbieter](../../data/oledb/reading-strings-into-the-ole-db-provider.md).  
  
3.  Bearbeiten Sie die eigenschaftenzuordnungen in MyProviderDS.h MyProviderSess.h und MyProviderRS.h. Der Assistent erstellt die eigenschaftenzuordnungen, die alle Eigenschaften enthalten, die ein Anbieter implementieren kann. Durchlaufen Sie die eigenschaftenzuordnungen, und entfernen oder kommentieren Sie die Eigenschaften, die Ihr Anbieter nicht unterstützen muss.  
  
4.  Aktualisieren Sie Makro, das in MyProviderRS.h gefunden werden kann. Ein Beispiel finden Sie unter [Speichern von Zeichenfolgen im OLE DB-Anbieter](../../data/oledb/storing-strings-in-the-ole-db-provider.md).  
  
5.  Wenn Sie zum Testen des Anbieters bereit sind, können Sie es testen, indem Sie versuchen, die der Anbieter in einer Anbieterenumeration finden. Beispiele für Testcode, die einen Anbieter in einer Enumeration sucht, finden Sie unter den [CATDB](https://github.com/Microsoft/VCSamples) und [DBVIEWER](https://github.com/Microsoft/VCSamples) Beispiele oder nur das Beispiel in [Implementieren eines einfachen Consumers](../../data/oledb/implementing-a-simple-consumer.md).  
  
6.  Fügen Sie alle zusätzlichen Schnittstellen gewünschten hinzu. Ein Beispiel finden Sie unter [Erweitern des einfachen schreibgeschützten Anbieters](../../data/oledb/enhancing-the-simple-read-only-provider.md).  
  
    > [!NOTE]
    >  Die Assistenten generieren standardmäßig Code, der OLE DB-Ebene 0 kompatibel ist. Um sicherzustellen, dass Ihre Anwendung auf Ebene 0 kompatibel bleiben, führen Sie keine der vom Assistenten generierten Schnittstellen aus dem Code entfernt.  
  
## <a name="see-also"></a>Siehe auch  
 [CATDB](https://github.com/Microsoft/VCSamples)   
 [DBVIEWER](https://github.com/Microsoft/VCSamples)