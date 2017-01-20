---
title: "Datenquellen und Sitzungen"
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
  - "Verbindungen [C++], Datenquelle"
  - "Datenquellen [C++], OLE DB"
  - "OLE DB-Consumervorlagen [C++], Datenquellen"
ms.assetid: 6ee52216-e082-4869-a1d6-ce561cfb76e5
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Datenquellen und Sitzungen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In der folgenden Abbildung sehen Sie die Klassen, die eine Verbindung mit einer Datenquelle und den Zugriff auf eine Datenquelle unterstützen.  Jede Klasse basiert auf einer standardmäßigen OLE DB\-Komponentenimplementierung.  
  
 ![Datenquelle und Sitzungsklassen](../../data/oledb/media/vcdatasourcesessionclasses.png "vcDataSourceSessionClasses")  
Datenquelle und Sitzungsklassen  
  
 Die Klassen sind:  
  
-   [CDataSource](../../data/oledb/cdatasource-class.md) Diese Klasse instanziiert das Datenquellenobjekt, das eine Verbindung zu einer Datenquelle mithilfe eines OLE DB\-Anbieters erstellt und verwaltet.  Die Datenquelle nimmt Informationen, z. B. die Datenquelladresse und Authentifizierungsinformationen, in Form einer Verbindungszeichenfolge an.  
  
     Häufig wird auch die Hilfsklasse [CEnumerator](../../data/oledb/cenumerator-class.md) vor dem Aufbau einer Verbindung verwendet, um eine Liste der in einem System verfügbaren registrierten Anbieter zu erhalten.  Dadurch können Sie einen Anbieter als Datenquelle auswählen.  Im Dialogfeld **Datenverknüpfungseigenschaften** wird diese Klasse beispielsweise verwendet, um die Liste der Anbieter auf der Registerkarte **Anbieter** auszufüllen.  Sie entspricht der **SQLBrowseConnect**\-Funktion oder der **SQLDriverConnect**\-Funktion.  
  
-   [CSession](../../data/oledb/csession-class.md) Diese Klasse instanziiert das Sitzungsobjekt, das eine einzelne Zugriffssitzung zur Datenquelle repräsentiert.  Sie können jedoch auch mehrere Sitzungen für eine Datenquelle erstellen.  Für jede Sitzung können Sie Rowsets, Befehle und andere Objekte erstellen, um auf Daten aus der Datenquelle zuzugreifen.  Die Sitzung behandelt Transaktionen.  
  
## Siehe auch  
 [OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)