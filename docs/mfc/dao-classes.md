---
title: "DAO-Klassen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DAO [C++], Klassen"
  - "Datenbankklassen [C++], DAO"
ms.assetid: b15d0cd6-328b-4288-9c19-d037a795db57
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# DAO-Klassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Diese Klassen können mit den anderen Anwendungsframeworkklassen, um einfachen Zugriff auf Datenbanken Datenzugriffsobjekt \(dao\)\- zu geben, die dasselbe Datenbankmodul wie Microsoft Visual Basic und Microsoft Access verwenden.  DAO\-Klassen können auf eine Vielzahl von Datenbanken auch zugreifen, für Treiber der Open Database Connectivity \(ODBC\) verfügbar sind.  
  
 Programme, die DAO\-Datenbanken verwenden, verfügen mindestens ein `CDaoDatabase`\-Objekt und ein `CDaoRecordset`\-Objekt.  
  
> [!NOTE]
>  Ab Visual C\+\+ .NET wird DAO von der Visual C\+\+\-Umgebung und den Assistenten nicht mehr unterstützt. \(Die DAO\-Klassen sind allerdings weiterhin enthalten und können verwendet werden.\)  Microsoft empfiehlt, dass Sie ODBC für neue MFC\-Projekte verwenden.  DAO sollte lediglich zur Verwaltung bereits bestehender Anwendungen eingesetzt werden.  
  
 [CDaoWorkspace](../mfc/reference/cdaoworkspace-class.md)  
 Verwaltet eine benannte, kennwortgeschützte, Datenbanksitzung der Anmeldung von z abzumelden.  Die meisten Programme verwenden den Standardarbeitsbereich.  
  
 [CDaoDatabase](../mfc/reference/cdaodatabase-class.md)  
 Eine Verbindung zu einer Datenbank, durch die Sie die Daten angewendet werden können.  
  
 [CDaoRecordset](../mfc/reference/cdaorecordset-class.md)  
 Stellt eine Gruppe von Datensätzen dar, die aus einer Datenquelle ausgewählt wurden.  
  
 [CDaoRecordView](../mfc/reference/cdaorecordview-class.md)  
 Eine Sicht, die Datenbankdatensätze in Steuerelementen anzeigt.  
  
 [CDaoQueryDef](../mfc/reference/cdaoquerydef-class.md)  
 Stellt eine Abfragedefinition, gewöhnlich eine dar, die in einer Datenbank gespeichert ist.  
  
 [CDaoTableDef](../mfc/reference/cdaotabledef-class.md)  
 Stellt die gespeicherte Definition einer Basistabelle oder einer angefügten Tabelle dar.  
  
 [CDaoException](../mfc/reference/cdaoexception-class.md)  
 Stellt eine Ausnahmebedingung dar, die aus den DAO\-Klassen entsteht.  
  
 [CDaoFieldExchange](../mfc/reference/cdaofieldexchange-class.md)  
 Unterstützt die Routinen für den DAO\-Datensatzfeldaustausch \(DAO record field exchange, DFX\), die von den DAO\-Datenbankklassen verwendet werden.  Sie normalerweise nicht direkt verwenden diese Klasse.  
  
## Verwandte Klassen  
 [CLongBinary](../mfc/reference/clongbinary-class.md)  
 Kapselt ein Handle für Speicher für ein Binary Large Object \(BLOB\), z eine Bitmap.  `CLongBinary`\-Objekte werden verwendet, um die große Datenobjekte zu verwalten, die in den Datenbanktabellen gespeichert werden.  
  
 [COleCurrency](../mfc/reference/colecurrency-class.md)  
 Wrapper für den OLE\-Automatisierungs\-Typ **WÄHRUNG**, ein arithmetischer Typ des Festkommas, mit 15 Ziffern vor dem Dezimaltrennzeichen und 4 Ziffern nach.  
  
 [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)  
 Wrapper für den OLE\-Automatisierungs\-Typ **DATUM**.  Stellt Datums\- und Uhrzeitwerte dar.  
  
 [COleVariant](../mfc/reference/colevariant-class.md)  
 Wrapper für den OLE\-Automatisierungs\-Typ **VARIANT**.  Daten in **VARIANT**s können in vielen Formaten gespeichert werden.  
  
## Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)