---
title: "Recordset: Scrollen (ODBC) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Move-Methode (Recordsets)"
  - "Navigation [C++], Recordsets"
  - "ODBC-Recordsets, Scrollen"
  - "Recordsets [C++], Anfang von"
  - "Recordsets [C++], Ende"
  - "Recordsets [C++], Verschieben in Datensätze"
  - "Recordsets [C++], Navigieren"
  - "Scrollen [C++], Recordsets"
ms.assetid: f38d2dcb-1e88-4e41-af25-98b00c276be4
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Recordset: Scrollen (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Thema bezieht sich auf die MFC\-ODBC\-Klassen.  
  
 Nachdem Sie ein Recordset geöffnet hatten, müssen Sie auf die Datensätze zugreifen, um ihren Wert anzuzeigen, Berechnungen durchzuführen, Berichte zu erstellen usw.  Das Scrollen ermöglicht es Ihnen, innerhalb des Recordsets von Datensatz zu Datensatz zu wechseln.  
  
 In diesem Thema wird Folgendes erläutert:  
  
-   [Scrollen von einem Datensatz zum anderen](#_core_scrolling_from_one_record_to_another)  
  
-   [Wann Scrollen unterstützt wird](#_core_when_scrolling_is_supported)  
  
##  <a name="_core_scrolling_from_one_record_to_another"></a> Scrollen von einem Datensatz zum anderen  
 Die `CRecordset`\-Klasse stellt für das Scrollen innerhalb eines Recordsets die **Move**\-Memberfunktionen bereit.  Diese Funktionen verschieben den aktuellen Datensatz um eine bestimmte Anzahl Rowsets.  Falls Sie das gesammelte Abrufen von Zeilen implementiert haben, verschiebt eine **Move**\-Operation das Recordset um die Größe des Rowsets.  Falls Sie das gesammelte Abrufen von Zeilen nicht implementiert haben, verschiebt jeder Aufruf einer **Move**\-Funktion das Recordset um jeweils einen Datensatz.  Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
> [!NOTE]
>  Beim Scrollen durch ein Recordset werden gelöschte Datensätze unter Umständen nicht übersprungen.  Weitere Informationen hierzu finden Sie unter dem Thema [IsDeleted](../Topic/CRecordset::IsDeleted.md)\-Memberfunktion.  
  
 Neben den **Move**\-Funktionen enthält `CRecordset` Memberfunktionen, mit denen Sie feststellen können, ob Sie über das Ende oder den Anfang des Recordsets gescrollt haben.  
  
 Rufen Sie die `CanScroll`\-Memberfunktion auf, um festzustellen, ob Scrollen im Recordset möglich ist.  
  
#### So scrollen Sie  
  
1.  Einen Datensatz oder ein Rowset vorwärts scrollen: Rufen Sie die [MoveNext](../Topic/CRecordset::MoveNext.md)\-Memberfunktion auf.  
  
2.  Einen Datensatz oder ein Rowset rückwärts scrollen: Rufen Sie die [MovePrev](../Topic/CRecordset::MovePrev.md)\-Memberfunktion auf.  
  
3.  Zum ersten Datensatz des Recordsets scrollen: Rufen Sie die [MoveFirst](../Topic/CRecordset::MoveFirst.md)\-Memberfunktion auf.  
  
4.  Zum letzten Datensatz des Recordsets oder zum letzten Rowset scrollen: Rufen Sie die [MoveLast](../Topic/CRecordset::MoveLast.md)\-Memberfunktion auf.  
  
5.  *N* Datensätze relativ zur aktuellen Position scrollen: Rufen Sie die [Move](../Topic/CRecordset::Move.md)\-Memberfunktion auf.  
  
#### So überprüfen Sie, ob das Ende oder der Anfang des Recordsets erreicht ist  
  
1.  Haben Sie über den letzten Datensatz hinaus gescrollt?  Rufen Sie die [IsEOF](../Topic/CRecordset::IsEOF.md)\-Memberfunktion auf.  
  
2.  Haben Sie \(rückwärts\) über den ersten Datensatz hinaus gescrollt?  Rufen Sie die [IsBOF](../Topic/CRecordset::IsBOF.md)\-Memberfunktion auf.  
  
 Im folgenden Codebeispiel werden beim Scrollen in beiden Richtungen mithilfe von `IsBOF` und `IsEOF` die Grenzen eines Recordsets ermittelt.  
  
```  
// Open a recordset; first record is current  
CCustSet rsCustSet( NULL );  
rsCustSet.Open( );  
  
if( rsCustSet.IsBOF( ) )  
    return;  
    // The recordset is empty  
  
// Scroll to the end of the recordset, past  
// the last record, so no record is current  
while ( !rsCustSet.IsEOF( ) )  
    rsCustSet.MoveNext( );  
  
// Move to the last record  
rsCustSet.MoveLast( );  
  
// Scroll to beginning of the recordset, before  
// the first record, so no record is current  
while( !rsCustSet.IsBOF( ) )  
    rsCustSet.MovePrev( );  
  
// First record is current again  
rsCustSet.MoveFirst( );  
```  
  
 `IsEOF` gibt einen Wert ungleich 0 \(null\) zurück, wenn der Recordset hinter dem letzten Datensatz platziert wird.  `IsBOF` gibt einen Wert ungleich 0 \(null\) zurück, wenn der Recordset vor dem ersten Datensatz \(vor allen Datensätzen\) platziert wird.  In beiden Fällen gibt es keinen aktuellen Datensatz, der bearbeitet werden kann.  Wenn Sie `MovePrev` aufrufen, während `IsBOF` bereits **TRUE** ist, oder wenn Sie `MoveNext` aufrufen, während `IsEOF` bereits **TRUE** ist, löst das Framework eine `CDBException` aus.  Sie können mit **IsBOF** und **IsEOF** auch feststellen, ob ein Recordset leer ist.  
  
 Weitere Informationen zur Recordsetnavigation finden Sie unter [Recordset: Lesezeichen und absolute Positionen \(ODBC\)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md).  
  
##  <a name="_core_when_scrolling_is_supported"></a> Wann Scrollen unterstützt wird  
 In seinem ursprünglichen Entwurf unterstützte SQL ausschließlich das Vorwärtsscrollen, aber ODBC erweitert diese Fähigkeiten.  Inwieweit das Scrollen unterstützt wird, hängt von den ODBC\-Treibern ab, mit denen die Anwendung ausgeführt wird, vom ODBC\-API\-Conformance\-Level des Treibers und davon, ob die ODBC\-Cursorbibliothek in den Speicher geladen ist.  Weitere Informationen finden Sie unter [ODBC](../../data/odbc/odbc-basics.md) und [ODBC: Die ODBC\-Cursorbibliothek](../../data/odbc/odbc-the-odbc-cursor-library.md).  
  
> [!TIP]
>  Die Verwendung der Cursorbibliothek ist optional.  Weitere Informationen finden Sie unter dem `bUseCursorLib`\-Parameter und `dwOptions`\-Parameter für [CDatabase::Open](../Topic/CDatabase::Open.md).  
  
> [!NOTE]
>  Im Unterschied zu den MFC\-DAO\-Klassen bieten die MFC\-ODBC\-Klassen keine **Find**\-Funktionen zum Suchen des nächsten \(oder vorherigen\) Datensatzes, der die angegebenen Kriterien erfüllt.  
  
## Siehe auch  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [CRecordset::CanScroll](../Topic/CRecordset::CanScroll.md)   
 [CRecordset::CheckRowsetError](../Topic/CRecordset::CheckRowsetError.md)   
 [Recordset: Filtern von Datensätzen \(ODBC\)](../../data/odbc/recordset-filtering-records-odbc.md)