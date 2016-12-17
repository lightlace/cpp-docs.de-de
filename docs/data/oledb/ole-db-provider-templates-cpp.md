---
title: "OLE&#160;DB-Anbietervorlagen (C++)"
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
  - "Datenbanken [C++], OLE DB-Vorlagen"
  - "OLE DB-Anbietervorlagen [C++], Informationen über OLE DB-Anbietervorlagen"
  - "OLE DB-Anbieter [C++], Informationen über Anbieter"
  - "Vorlagen [C++], OLE DB"
ms.assetid: fccff85f-2af8-4500-82bd-6312d28a74b8
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# OLE&#160;DB-Anbietervorlagen (C++)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE DB ist ein wichtiger Bestandteil der Universal Data Access\-Strategie von Microsoft.  Das OLE DB\-Design ermöglicht leistungsfähige Datenzugriffe von beliebigen Datenquellen.  OLE DB unterstützt die Anzeige beliebiger tabellarischer Daten, unabhängig davon, ob die Daten aus einer Datenbank stammen.  Diese Flexibilität gewährleistet eine enorme Leistungsfähigkeit.  
  
 Wie bereits unter [OLE DB\-Consumer und \-Anbieter](../../data/oledb/ole-db-consumers-and-providers.md) erörtert, basiert OLE DB auf dem Consumer\-\/Anbieter\-Konzept.  Der Consumer fordert Daten an, während der Anbieter Daten im Tabellenformat an den Consumer zurückgibt.  Im Hinblick auf die Programmierung besteht der wichtigste Aspekt dieses Modells darin, dass jeder vom Consumer auszuführende Aufruf vom Anbieter implementiert werden muss.  
  
## Was ist ein Anbieter?  
 Ein OLE DB\-Anbieter umfasst eine Reihe von COM\-Objekten, die Schnittstellenaufrufe von einem Consumerobjekt bedienen. Dabei werden Daten in tabellarischem Format von einer beständigen Quelle \(dem so genannten Datenspeicher\) an den Consumer übermittelt.  
  
 Anbieter können einfach oder komplex sein.  Der Anbieter kann funktionelle Mindestanforderungen erfüllen oder eine voll ausgestattete Produktionseinheit darstellen, die weitere Schnittstellen implementiert.  Ein Anbieter kann eine Tabelle zurückgeben und einen Client zum Festlegen des Formats dieser Tabelle berechtigen, und er kann diese Daten verarbeiten.  
  
 Jeder Anbieter implementiert ein Standardset von COM\-Objekten, durch die Clientanforderungen behandelt werden. Dies bedeutet im Allgemeinen, dass jeder OLE DB\-Consumer unabhängig von der jeweiligen Sprache \(z. B. C\+\+ und Basic\) auf die Daten eines beliebigen Anbieters zugreifen kann.  
  
 Jedes COM\-Objekt enthält mehrere Schnittstellen, von denen einige erforderlich und andere optional sind.  Durch die Implementierung erforderlicher Schnittstellen gewährleistet der Anbieter ein Mindestmaß an Funktionalität \(die so genannte Kompatibilität\), die jeder Client unterstützen sollte.  Jeder Anbieter kann optionale Schnittstellen implementieren, um zusätzliche Funktionen bereitzustellen.  Unter [Architektur von OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md) werden diese Schnittstellen ausführlich beschrieben.  Um festzustellen, ob eine bestimmte Schnittstelle von einem Anbieter unterstützt wird, sollte der Client immer `QueryInterface` aufrufen.  
  
## Unterstützung gemäß OLE DB\-Spezifikation  
 Die OLE DB\-Anbietervorlagen unterstützen die OLE DB\-Spezifikation, Version 2.7.  OLE DB\-Anbietervorlagen ermöglichen die Implementierung von Level 0\-Anbietern.  Im Anbieterbeispiel werden zum Beispiel die Vorlagen zum Implementieren eines SQL\-fremden \(MSDOS\-\) Befehlsservers verwendet, der zum Durchsuchen des Dateisystems den DOS\-Befehl DIR ausführt.  Im Anbieterbeispiel werden die Verzeichnisinformationen in einem Rowset zurückgegeben, das den OLE DB\-Standardmechanismus für die Rückgabe tabellarischer Daten darstellt.  
  
 Der einfachste Anbietertyp, der von den OLE DB\-Vorlagen unterstützt wird, ist ein schreibgeschützter, befehlsloser Anbieter.  Natürlich werden neben der Erstellung von Lesezeichen sowie Lese\-\/Schreibfunktionen auch Anbieter unterstützt, die Befehle verwenden.  Lese\-\/Schreibanbieter können durch zusätzlichen Code implementiert werden.  Dynamische Rowsets und Transaktionen werden von der aktuellen Version derzeit nicht unterstützt, können jedoch ggf. hinzugefügt werden.  
  
## Wann sollte ein OLE DB\-Anbieter erstellt werden?  
 Es ist nicht immer erforderlich, einen eigenen Anbieter zu erstellen. Microsoft stellt im Dialogfeld **Datenverknüpfungseigenschaften** von Visual C\+\+ mehrere vorgefertigte Standardanbieter zur Verfügung.  Der Hauptgrund für das Erstellen eines OLE DB\-Anbieters besteht darin, die Vorteile der Universal Data Access\-Strategie zu nutzen.  Einige Vorteile dieser Strategie:  
  
-   Datenzugriffe in beliebigen Programmiersprachen, z. B. C\+\+, Basic und Visual Basic Scripting Edition.  Verschiedene Programmierer in der Organisation können unabhängig von der verwendeten Programmiersprache auf dieselbe Weise auf dieselben Daten zugreifen.  
  
-   Anderen Datenquellen, z. B. SQL Server, Excel und Access, können Daten zur Verfügung gestellt werden.  Dieses Feature ist z. B. äußerst hilfreich, wenn Daten zwischen unterschiedlichen Formaten übertragen werden sollen.  
  
-   Durchführen von Operationen, die datenquellenübergreifend \(heterogen\) erfolgen.  Dies stellt ein effizientes Feature für das Data Warehousing dar.  Durch die Verwendung von OLE DB\-Anbietern können Daten das systemeigene Format beibehalten, während weiterhin mittels einer einfachen Operation darauf zugegriffen werden kann.  
  
-   Zusätzliche Datenverarbeitungsfunktionen, z. B. die Abfrageverarbeitung.  
  
-   Gesteigerte Leistung bei Datenzugriffen, indem Datenänderungen gesteuert werden können.  
  
-   Höhere Stabilität.  Die Verwendung von proprietären Datenformaten, auf die lediglich ein Programmierer zugreifen kann, bedeutet ein Risiko.  Durch die Verwendung von OLE DB\-Anbietern können proprietäre Formate allen Programmierern zugänglich gemacht werden.  
  
## Schreibgeschützte und aktualisierbare Anbieter  
 Hinsichtlich Komplexität und Funktionalität können Anbieter große Unterschiede aufweisen.  Daher ist es hilfreich, Anbieter in schreibgeschützte und aktualisierbare Anbieter zu kategorisieren:  
  
-   In Visual C\+\+ 6.0 wurden lediglich schreibgeschützte Anbieter unterstützt.  Unter [Erstellen eines OLE DB\-Anbieters](../../data/oledb/creating-an-ole-db-provider.md) wird erläutert, wie ein schreibgeschützter Anbieter erstellt wird.  
  
-   Visual C\+\+ .NET unterstützt aktualisierbare Anbieter, die den Datenspeicher aktualisieren \(d. h. darin schreiben\) können.  Weitere Informationen finden Sie unter [Erstellen eines aktualisierbaren Anbieters](../../data/oledb/creating-an-updatable-provider.md). [UpdatePV](assetId:///c8bed873-223c-4a7d-af55-f90138c6f38f) ist ein Beispiel für einen aktualisierbaren Anbieter.  
  
 Weitere Informationen finden Sie unter:  
  
-   [Architektur von OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)  
  
-   [Erstellen eines OLE DB\-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)  
  
-   [OLE DB\-Programmierung](../../data/oledb/ole-db-programming.md)  
  
## Siehe auch  
 [Datenzugriff](../Topic/Data%20Access%20in%20Visual%20C++.md)   
 [OLE DB SDK\-Dokumentation](https://msdn.microsoft.com/en-us/library/ms722784.aspx)   
 [OLE DB\-Programmiererreferenz](https://msdn.microsoft.com/en-us/library/ms713643.aspx)