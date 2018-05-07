---
title: DAO-Klassen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.data
dev_langs:
- C++
helpviewer_keywords:
- database classes [MFC], DAO
- DAO [MFC], classes
ms.assetid: b15d0cd6-328b-4288-9c19-d037a795db57
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f43595ca5f688372a70999231ceebec5282cd3b6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="dao-classes"></a>DAO-Klassen
Diese Klassen arbeiten Sie mit der anderen Anwendung Framework-Klassen einfachen Zugriff gewähren möchten (Datenzugriffsobjekt)-Datenbanken, die das gleiche Datenbankmodul als Microsoft Visual Basic und Microsoft Access zu verwenden. DAO-Klassen können auch eine Vielzahl von Datenbanken zugreifen, für die Open Database Connectivity (ODBC)-Treiber zur Verfügung stehen.  
  
 Programme, die DAO-Datenbanken zugreifen müssen mindestens eine `CDaoDatabase` Objekt und ein `CDaoRecordset` Objekt.  
  
> [!NOTE]
>  Die Visual C++-Umgebung und den Assistenten nicht mehr unterstützt (obwohl die DAO-Klassen enthalten sind, und Sie weiterhin verwenden können,). Microsoft empfiehlt die Verwendung von ODBC für neue MFC-Projekte. Sie sollten nur DAO verwenden, in die Verwaltung bereits vorhandener Anwendungen.  
  
 [CDaoWorkspace](../mfc/reference/cdaoworkspace-class.md)  
 Verwaltet eine benannte, kennwortgeschützte datenbanksitzung von der Anmeldung bis zu Abmeldung. Die meisten Programme verwenden Sie den Arbeitsbereich "Standard".  
  
 [CDaoDatabase](../mfc/reference/cdaodatabase-class.md)  
 Eine Verbindung mit einer Datenbank, die über der die Daten bearbeitet werden können.  
  
 [CDaoRecordset](../mfc/reference/cdaorecordset-class.md)  
 Stellt eine Gruppe von Datensätzen dar, die aus einer Datenquelle ausgewählt wurden.  
  
 [CDaoRecordView](../mfc/reference/cdaorecordview-class.md)  
 Eine Sicht, die Datenbankdatensätze in Steuerelementen anzeigt.  
  
 [CDaoQueryDef](../mfc/reference/cdaoquerydef-class.md)  
 Stellt eine Abfragedefinition, in der Regel eine in einer Datenbank gespeichert.  
  
 [CDaoTableDef](../mfc/reference/cdaotabledef-class.md)  
 Stellt die gespeicherte Definition einer Basistabelle oder einer angefügten Tabelle dar.  
  
 [CDaoException](../mfc/reference/cdaoexception-class.md)  
 Stellt eine Ausnahmebedingung, die von den DAO-Klassen dar.  
  
 [CDaoFieldExchange](../mfc/reference/cdaofieldexchange-class.md)  
 Unterstützt die Routinen für den DAO-Datensatzfeldaustausch (DAO record field exchange, DFX), die von den DAO-Datenbankklassen verwendet werden. Diese Klasse wird normalerweise nicht direkt verwendet.  
  
## <a name="related-classes"></a>Verwandte Klassen  
 [CLongBinary](../mfc/reference/clongbinary-class.md)  
 Kapselt ein Handle für den Speicher für ein binary large Object (BLOB), z. B. eine Bitmap an. `CLongBinary` Objekte werden verwendet, um große Datenmengen-Objekte, die in Datenbanktabellen gespeichert zu verwalten.  
  
 [COleCurrency](../mfc/reference/colecurrency-class.md)  
 Wrapper für den Typ der OLE-Automatisierung **Währung**, Festkommanotation in jedem Fall arithmetischen Typs, mit 15 Stellen vor dem Dezimaltrennzeichen und 4 Ziffern nach dem.  
  
 [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)  
 Wrapper für den Typ der OLE-Automatisierung **Datum**. Stellt die Datums-und Uhrzeitwerte dar.  
  
 [COleVariant](../mfc/reference/colevariant-class.md)  
 Wrapper für den Typ der OLE-Automatisierung **VARIANT**. Daten in **VARIANT**s kann in vielen verschiedenen Formaten gespeichert werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)

