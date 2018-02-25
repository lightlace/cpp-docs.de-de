---
title: OLE DB-Anbietervorlagen (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers [C++], about providers
- databases [C++], OLE DB templates
- OLE DB provider templates [C++], about OLE DB provider templates
- templates [C++], OLE DB
ms.assetid: fccff85f-2af8-4500-82bd-6312d28a74b8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 255a61d7cff661406da327de79c6a726ffb60bab
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="ole-db-provider-templates-c"></a>OLE DB-Anbietervorlagen (C++)
OLE DB ist ein wichtiger Teil der Microsoft Universal Data Access-Strategie. Das OLE DB-Design ermöglicht es, hohe Leistung Datenzugriff aus einer beliebigen Datenquelle. Keine Tabellendaten können über OLE DB angezeigt werden, unabhängig davon, ob sie aus einer Datenbank stammt. Die Flexibilität bietet Ihnen eine enorme Power.  
  
 Wie in beschrieben [OLE DB-Consumer und-Anbieter](../../data/oledb/ole-db-consumers-and-providers.md), OLE DB-Consumer und-Anbieter verwendet. Der Consumer fordert Daten; der Anbieter, die Daten in einem tabellarischen Format an den Consumer zurückgegeben wird. Hinsichtlich der Programmierung ist die wichtigste Implikation dieses Modell der Anbieter muss jeder Aufruf implementieren, die der Consumer vornehmen kann.  
  
## <a name="what-is-a-provider"></a>Was ist ein Anbieter?  
 OLE DB-Anbieter ist ein Satz von COM-Objekten, die Aufrufe aus einem Consumerobjekt Interface dienen übertragen von Daten in tabellarischer Form aus einer permanenten Quelle (als Datenspeicher bezeichnet) an den Consumer.  
  
 Anbieter können einfach oder komplex sein. Der Anbieter kann eine minimale Menge an Funktionalität oder ein vollständiges Produktion Qualität Anbieter unterstützen, durch mehrere Schnittstellen implementieren. Ein Anbieter kann geben eine Tabelle zurück, ermöglichen es dem Client wird das Format der Tabelle bestimmt und führen Operationen für diese Daten.  
  
 Jeder Anbieter implementiert einen Standardsatz von COM-Objekte für die Verarbeitung von Anforderungen vom Client mit einer standardmäßigen Bedeutung, dass jeder OLE DB-Consumer Daten von einem Anbieter, unabhängig von der Sprache (z. B. C++ und grundlegende) zugreifen kann.  
  
 Jede COM-Objekt enthält mehrere Schnittstellen, von denen einige erforderlich sind und von denen einige sind optional. Durch die Implementierung der obligatorischen Schnittstellen können gewährleistet der Anbieter ein Mindestmaß an Funktionen (so genannte Kompatibilität), die einem beliebigen Client verwenden werden sollen. Ein Anbieter kann optionale Schnittstellen, um zusätzliche Funktionen bieten implementieren. [Der OLE DB-Vorlagen-Anbieterarchitektur](../../data/oledb/ole-db-provider-template-architecture.md) werden diese Schnittstellen im Detail beschrieben. Rufen Sie der Client sollte immer `QueryInterface` zu bestimmen, ob eine bestimmte Schnittstelle von einem Anbieter unterstützt.  
  
## <a name="ole-db-specification-level-support"></a>OLE DB-Spezifikation Unterstützung auf Hostebene  
 Der OLE DB-Anbietervorlagen unterstützen die Spezifikation der OLE DB Version 2.7. Verwenden den OLE DB-Anbietervorlagen, können Sie einen Ebene 0 kompatibel Anbieter implementieren. Die Anbieter-Beispiel verwendet die Vorlagen z. B. ein Servers Befehlsservers Befehl zu implementieren, das den DOS-Befehl DIR im Dateisystem Abfrage ausgeführt wird. Die Anbieter-Beispiel gibt die Verzeichnisinformationen in einem Rowset, also den OLE DB-Standardmechanismus zum Zurückgeben von tabellarischen Daten zurück.  
  
 Die einfachste Art des Anbieters, die von der OLE DB-Vorlagen unterstützt handelt es sich um eine nur-Lese Anbieter mit keine Befehle. Anbieter mit Befehlen werden ebenfalls unterstützt, wie das Hinzufügen von Lesezeichen und Lese-/Schreibzugriff-Funktion sind. Sie können einen Lese-/Schreibzugriff-Anbieter implementieren, indem Sie zusätzlichen Code schreiben. Dynamische Rowsets und Transaktionen werden von der aktuellen Version nicht unterstützt, jedoch können Sie diese hinzufügen, wenn Sie möchten.  
  
## <a name="when-do-you-need-to-create-an-ole-db-provider"></a>Auf diese Weise müssen Sie beim Erstellen eines OLE DB-Anbieters?  
 Erstellen Sie einen eigenen Anbieter ist nicht immer erforderlich; Microsoft bietet mehrere vorgefertigte Anbieter in der **Datenlinkeigenschaften** Dialogfeld in Visual C++. Der Hauptgrund zum Erstellen eines OLE DB-Anbieters ist die Universal Data Access-Strategie nutzen. Daher sind einige der Vorteile besteht:  
  
-   Der Datenzugriff mithilfe einer beliebigen Sprache wie C++, Basic und Visual Basic Scripting Edition. Sie können verschiedene Programmierer in Ihrer Organisation Zugriff auf die gleichen Daten auf die gleiche Weise, unabhängig davon, welche Sprache sie verwenden.  
  
-   Verfügbarmachen der Daten zu anderen Datenquellen wie SQL Server, Excel und Access. Dies kann sehr nützlich, wenn Sie Daten zwischen unterschiedlichen Formaten übertragen möchten.  
  
-   Teilnehmen an Cross-Datenquelle (heterogene)-Vorgänge. Dies kann eine sehr effektive Möglichkeit, Datawarehousing sein. Mithilfe von OLE DB-Anbieter können Sie Daten im systemeigenen Format speichern und weiterhin in der Lage für den Zugriff darauf in ein einfacher Vorgang.  
  
-   Hinzufügen von zusätzlichen Funktionen für die Daten, wie die abfrageverarbeitung.  
  
-   Erhöhen der Leistung beim Zugriff auf Daten durch steuern, wie es bearbeitet wird.  
  
-   Höhere Stabilität. Wenn Sie ein proprietäres Format haben, nur ein Programmierer zugreifen kann, Sie sind gefährdet. OLE DB-Anbieter verwenden, können Sie diese proprietäre Format für alle Ihre Programmierer öffnen.  
  
## <a name="read-only-and-updatable-providers"></a>Nur-Lese und aktualisierbare Anbieter  
 Anbieter können Komplexität und Funktionalität erheblich variieren. Es eignet sich zum Kategorisieren von Anbietern in nur-Lese und aktualisierbare Anbieter:  
  
-   Visual C++ 6.0 unterstützt nur schreibgeschützte Anbieter. [Erstellen einen OLE DB-Anbieter](../../data/oledb/creating-an-ole-db-provider.md) erläutert, wie einen nur-Lese Anbieter erstellt.  
  
-   Visual C++ unterstützt aktualisierbare Anbieter, die aktualisiert werden können (Schreiben) den Datenspeicher. Informationen zu aktualisierbaren Anbietern finden Sie unter [Erstellen eines aktualisierbaren Anbieters](../../data/oledb/creating-an-updatable-provider.md); das [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f) Beispiel ist ein Beispiel eines aktualisierbaren Anbieters.  
  
 Weitere Informationen finden Sie unter:  
  
-   [Architektur von OLE DB-Anbieter](../../data/oledb/ole-db-provider-template-architecture.md)  
  
-   [Erstellen eines OLE DB-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)  
  
-   [OLE DB-Programmierung](../../data/oledb/ole-db-programming.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Datenzugriff](../data-access-in-cpp.md)   
 [OLE DB-SDK-Dokumentation](https://msdn.microsoft.com/en-us/library/ms722784.aspx)   
 [OLE DB-Programmierreferenz](https://msdn.microsoft.com/en-us/library/ms713643.aspx)