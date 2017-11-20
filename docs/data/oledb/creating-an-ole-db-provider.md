---
title: Erstellen eines OLE DB-Anbieters | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE DB providers, creating
- OLE DB provider templates, creating providers
ms.assetid: f73017c3-c89f-41a6-a306-ea992cf6092c
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 07060be0c14adb4d509c23ab88914de4494e6862
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="creating-an-ole-db-provider"></a>Erstellen eines OLE DB-Anbieters
Die empfohlene Methode zum Erstellen eines OLE DB-Anbieters ist die Verwendung des Assistenten ein ATL COM-Projekt und einen Anbieter erstellen und ändern dann die Dateien mithilfe der OLE DB-Vorlagen. Wie Sie Ihren Anbieter anpassen, können nicht benötigte Eigenschaften auskommentieren und optionale Schnittstellen hinzufügen.  
  
 Die grundlegenden Schritte lauten wie folgt:  
  
1.  Verwenden Sie die ATL-Projekt-Assistent zum Erstellen der grundlegenden Projektdateien und die ATL OLE DB-Anbieter-Assistenten aus, um den Anbieter zu erstellen (Wählen Sie **ATL-OLE DB-Anbieter** aus dem Visual C++-Ordner im **Klasse hinzufügen**).  
  
2.  Ändern Sie den Code in die `Execute` Methode in der Datei CMyProviderRS.h. Ein Beispiel finden Sie unter [Einlesen von Zeichenfolgen in den OLE DB-Anbieter](../../data/oledb/reading-strings-into-the-ole-db-provider.md).  
  
3.  Bearbeiten Sie die eigenschaftenzuordnungen in MyProviderDS.h MyProviderSess.h und MyProviderRS.h. Der Assistent erstellt eigenschaftenzuordnungen, die alle Eigenschaften enthalten, die ein Anbieter implementieren kann. Durchlaufen der eigenschaftenzuordnungen, und entfernen oder kommentieren Sie Eigenschaften, die Ihr Anbieter nicht unterstützen muss.  
  
4.  Aktualisieren Sie Makro, das in MyProviderRS.h gefunden werden kann. Ein Beispiel finden Sie unter [Speichern von Zeichenfolgen im OLE DB-Anbieter](../../data/oledb/storing-strings-in-the-ole-db-provider.md).  
  
5.  Wenn Sie zum Testen des Anbieters bereit sind, können Sie sie testen, indem versucht wird, finden Sie den Anbieter in einer Anbieterenumeration. Beispiele von Beispieltestcode ein Anbieters in einer Enumeration finden Sie in der [CATDB](http://msdn.microsoft.com/en-us/003d516b-2bf6-444e-8be5-4ebaa0b66046) und [DBVIEWER](http://msdn.microsoft.com/en-us/07620f99-c347-4d09-9ebc-2459e8049832) Beispiele oder nur das Beispiel in [Implementieren eines einfachen Consumers](../../data/oledb/implementing-a-simple-consumer.md).  
  
6.  Fügen Sie zusätzlichen gewünschte Schnittstellen hinzu. Ein Beispiel finden Sie unter [Erweitern des einfachen schreibgeschützten Anbieters](../../data/oledb/enhancing-the-simple-read-only-provider.md).  
  
    > [!NOTE]
    >  Die Assistenten generieren standardmäßig Code, der OLE DB-Ebene 0 kompatibel ist. Um sicherzustellen, dass Ihre Anwendung auf Ebene 0 kompatibel bleiben, bauen Sie keine der vom Assistenten generierten Schnittstellen aus dem Code.  
  
## <a name="see-also"></a>Siehe auch  
 [CATDB](http://msdn.microsoft.com/en-us/003d516b-2bf6-444e-8be5-4ebaa0b66046)   
 [DIESES BEISPIEL](http://msdn.microsoft.com/en-us/07620f99-c347-4d09-9ebc-2459e8049832)