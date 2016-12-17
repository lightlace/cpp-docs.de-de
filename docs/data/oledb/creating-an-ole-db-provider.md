---
title: "Erstellen eines OLE&#160;DB-Anbieters"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE DB-Anbietervorlagen, Erstellen von Anbietern"
  - "OLE DB-Anbieter, Erstellen"
ms.assetid: f73017c3-c89f-41a6-a306-ea992cf6092c
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Erstellen eines OLE&#160;DB-Anbieters
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die empfohlene Methode zum Erstellen eines OLE DB\-Anbieters ist die Verwendung des Assistenten: Sie erstellen ein ATL COM\-Projekt sowie einen Anbieter und ändern dann die Dateien mithilfe der OLE DB\-Vorlagen entsprechend.  Während Sie den Anbieter anpassen, können Sie nicht benötigte Eigenschaften auskommentieren und optionale Schnittstellen hinzufügen.  
  
 Die folgenden Schritte sind notwendig:  
  
1.  Erstellen Sie die grundlegenden Projektdateien mit dem ATL\-Projekt\-Assistenten und den Anbieter mit dem ATL\-OLE DB\-Anbieter\-Assistenten. \(Wählen Sie unter **Klasse hinzufügen** aus dem Visual C\+\+\-Ordner **ATL\-OLEDB\-Anbieter** aus.\)  
  
2.  Ändern Sie in der Datei CMyProviderRS.h den Code der `Execute`\-Methode.  Ein Beispiel finden Sie unter [Einlesen von Zeichenfolgen in den OLE DB\-Anbieter](../../data/oledb/reading-strings-into-the-ole-db-provider.md).  
  
3.  Bearbeiten Sie die Eigenschaftenzuordnungen in MyProviderDS.h, MyProviderSess.h und MyProviderRS.h.  Der Assistent erstellt Eigenschaftenzuordnungen mit allen Eigenschaften, die von einem Anbieter implementiert werden können.  Durchsuchen Sie die Eigenschaftenzuordnungen, und entfernen Sie Eigenschaften, die nicht vom Anbieter unterstützt werden müssen, oder kommentieren Sie diese aus.  
  
4.  Aktualisieren Sie in der Datei MyProviderRS.h die PROVIDER\_COLUMN\_MAP.  Ein Beispiel finden Sie unter [Speichern von Zeichenfolgen im OLE DB\-Anbieter](../../data/oledb/storing-strings-in-the-ole-db-provider.md).  
  
5.  Wenn Sie bereit sind, den Anbieter zu testen, können Sie diese Aufgabe ausführen, indem Sie herausfinden, ob der Anbieter in einer Anbieterenumeration aufgeführt wird.  Beispieltestcode zum Suchen eines Anbieters in einer Enumeration finden Sie in den Beispielen [CATDB](assetId:///003d516b-2bf6-444e-8be5-4ebaa0b66046) und [DBVIEWER](assetId:///07620f99-c347-4d09-9ebc-2459e8049832) oder in dem Beispiel unter [Implementieren eines einfachen Consumers](../../data/oledb/implementing-a-simple-consumer.md).  
  
6.  Fügen Sie gegebenenfalls weitere Schnittstellen hinzu.  Ein Beispiel finden Sie unter [Erweitern des einfachen schreibgeschützten Anbieters](../../data/oledb/enhancing-the-simple-read-only-provider.md).  
  
    > [!NOTE]
    >  Die Assistenten generieren standardmäßig Code, der mit OLE DB Level 0 kompatibel ist.  Um sicherzustellen, dass die Anwendungskompatibilität mit Level 0 erhalten bleibt, sollten Sie keine vom Assistenten generierten Schnittstellen aus dem Code entfernen.  
  
## Siehe auch  
 [CATDB](assetId:///003d516b-2bf6-444e-8be5-4ebaa0b66046)   
 [DBVIEWER](assetId:///07620f99-c347-4d09-9ebc-2459e8049832)