---
title: Datenquellen und Sitzungen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- data sources [C++], OLE DB
- connections [C++], data source
- OLE DB consumer templates [C++], data sources
ms.assetid: 6ee52216-e082-4869-a1d6-ce561cfb76e5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d93f6aba8e9fad27054c731d37e6df28b54eacda
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="data-sources-and-sessions"></a>Datenquellen und Sitzungen
Die folgende Abbildung zeigt die Klassen, die eine Verbindung mit und Zugreifen auf eine Datenquelle unterstützen. Jede Klasse basiert auf einer standardmäßigen Implementierung der OLE DB-Komponente.  
  
 ![Daten-Datenquelle und Sitzungsklassen](../../data/oledb/media/vcdatasourcesessionclasses.gif "Vcdatasourcesessionclasses")  
Datenquelle und Sitzungsklassen  
  
 Die Klassen sind:  
  
-   [CDataSource](../../data/oledb/cdatasource-class.md) diese Klasse instanziiert das Datenquellenobjekt, das eine Verbindung mit einer Datenquelle über einen OLE DB-Anbieter erstellt und verwaltet. Die Datenquelle nimmt Informationen wie die Adresse und die Authentifizierung Datenquelleninformationen in Form einer Verbindungszeichenfolge.  
  
     Es ist auch zu beachten, dass die Hilfsklasse [CEnumerator](../../data/oledb/cenumerator-class.md) wird häufig verwendet werden, bevor eine Verbindung hergestellt wird, um eine Liste der verfügbaren Anbieter registriert auf einem System abzurufen. Dadurch können Sie einen Anbieter als Datenquelle auswählen. Z. B. die **Datenlinkeigenschaften** Dialogfeld verwendet diese Klasse zum Auffüllen der Liste der Anbieter auf dem **Anbieter** Registerkarte. Dies entspricht der **SQLBrowseConnect** oder **SQLDriverConnect** Funktion.  
  
-   [CSession](../../data/oledb/csession-class.md) diese Klasse instanziiert das Sitzungsobjekt, das eine einzelnen Access-Sitzung mit der Datenquelle darstellt. Allerdings können Sie mehrere Sitzungen für eine Datenquelle erstellen. Für jede Sitzung können Sie Rowsets, Befehle und anderer Objekte, den Zugriff auf Daten aus der Datenquelle erstellen. Die Sitzung behandelt Transaktionen.  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)