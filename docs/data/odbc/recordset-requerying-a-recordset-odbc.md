---
title: "Recordset: Erneutes Abfragen eines Recordsets (ODBC)"
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
  - "ODBC-Recordsets, Erneutes Abfragen"
  - "Recordsets, Erneutes Abfragen"
  - "Aktualisieren von Recordsets"
  - "Requery-Methode"
  - "Erneutes Abfragen von Recordsets"
ms.assetid: 4ebc3b5b-5b91-4f51-a967-245223c6b8e1
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Recordset: Erneutes Abfragen eines Recordsets (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Thema bezieht sich auf die MFC\-ODBC\-Klassen.  
  
 In diesem Thema wird erläutert, wie Sie ein Recordset\-Objekt durch Aufruf seiner [Requery](../Topic/CRecordset::Requery.md)\-Memberfunktion dazu verwenden können, sich selbst in der Datenbank neu abzufragen \(zu aktualisieren\).  
  
 Die Hauptgründe für die Neuabfrage eines Recordsets sind:  
  
-   Die von Ihnen oder anderen Benutzern neu hinzugefügten und gelöschten Datensätze sollen richtig angezeigt werden \(die gelöschten Datensätze werden bereits richtig im Recordset widergespiegelt\).  
  
-   Das Recordset soll aufgrund geänderter Parameterwerte aktualisiert werden.  
  
##  <a name="_core_bringing_the_recordset_up_to_date"></a> Aktualisieren des Recordsets  
 Sie werden das Recordset\-Objekt gelegentlich neu abfragen müssen, um es zu aktualisieren.  In einer Mehrbenutzerdatenbankumgebung können andere Benutzer innerhalb der Lebensdauer des Recordsets Änderungen an den Daten vornehmen.  Weitere Informationen darüber, wann das Recordset von anderen Benutzern vorgenommene Änderungen widerspiegelt und wann im Gegenzug von Ihnen vorgenommene Änderungen in den Recordsets anderer Benutzer widergespiegelt werden, finden Sie in unter [Recordset: Datensatzaktualisierung durch Recordsets \(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md) und [Dynaset](../../data/odbc/dynaset.md).  
  
##  <a name="_core_requerying_based_on_new_parameters"></a> Neuabfragen mit geänderten Parameterwerten  
 Ein anderer wichtiger Verwendungszweck für [Requery](../Topic/CRecordset::Requery.md) ist das Auswählen einer neuen Gruppe von Datensätzen, wenn sich Parameterwerte geändert haben.  
  
> [!TIP]
>  Die Geschwindigkeit der Abfrage ist wahrscheinlich wesentlich größer, wenn Sie **Requery** mit geänderten Parameterwerten aufrufen, als dies bei einem erneuten Aufruf von **Open** der Fall ist.  
  
##  <a name="_core_requerying_dynasets_vs.._snapshots"></a> Neuabfragen von Dynasets und Momentaufnahmen  
 Da Dynasets eine Gruppe von Datensätzen mit dynamischen, aktuellen Daten repräsentieren sollen, werden Sie Dynasets häufig abfragen, um die Ergänzungen anderer Benutzer widerzuspiegeln.  Momentaufnahmen sind dagegen insofern praktisch, als Sie sich darauf verlassen können, dass ihr Inhalt gleich bleibt, während Sie Berichte erstellen, Summen berechnen usw.  Trotzdem gibt es gelegentlich die Notwendigkeit, auch eine Momentaufnahme neu abzufragen.  In einer Mehrbenutzerumgebung kann bei Momentaufnahmedaten die Synchronisierung mit der Datenquelle verloren gehen, wenn andere Benutzer die Datenbank ändern.  
  
#### So fragen Sie ein Recordset\-Objekt neu ab  
  
1.  Rufen Sie die [Requery](../Topic/CRecordset::Requery.md)\-Memberfunktion des Objekts auf.  
  
 Alternativ können Sie auch das ursprüngliche Recordset schließen und erneut öffnen.  In beiden Fällen repräsentiert das neue Recordset den aktuellen Zustand der Datenquelle.  
  
 Ein Beispiel hierzu finden Sie unter [Füllen eines Listenfelds aus einem zweiten Recordset](../../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md).  
  
> [!TIP]
>  Zur Optimierung der **Requery**\-Leistung vermeiden Sie Änderungen am [Filter](../../data/odbc/recordset-filtering-records-odbc.md) oder der [Sortierung](../../data/odbc/recordset-sorting-records-odbc.md) des Recordsets.  Ändern Sie vor dem Aufruf von **Requery** ausschließlich den Parameterwert.  
  
 Wenn beim Aufruf von **Requery** ein Fehler auftritt, können Sie versuchen, den Aufruf noch einmal durchzuführen. Andernfalls sollte die Anwendung ordnungsgemäß beendet werden.  Beim Aufruf von **Requery** oder **Open** kann eine ganze Reihe von Fehlern auftreten.  Es kann z. B. ein Netzwerkfehler auftreten oder zwischen dem Zeitpunkt, an dem die alten Daten verworfen werden und dem Zeitpunkt, an dem die neuen Daten abgerufen werden, könnte ein anderer Benutzer den exklusiven Zugriff erhalten. Die Tabelle, auf die sich das Recordset bezieht, könnte jedoch auch gelöscht werden.  
  
## Siehe auch  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [Recordset: Dynamisches Binden von Datenspalten \(ODBC\)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)   
 [Recordset: Erstellen und Schließen von Recordsets \(ODBC\)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)