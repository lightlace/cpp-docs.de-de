---
title: 'Recordset: Scrollen (ODBC) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- recordsets [C++], end of
- recordsets [C++], beginning of
- navigation [C++], recordsets
- recordsets [C++], moving to records
- ODBC recordsets, scrolling
- recordsets [C++], navigating
- scrolling [C++], recordsets
- Move method (recordsets)
ms.assetid: f38d2dcb-1e88-4e41-af25-98b00c276be4
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 34dcfb9cb1d45710accba2ee6155e3c741b727be
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="recordset-scrolling-odbc"></a>Recordset: Scrollen (ODBC)
Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.  
  
 Nachdem Sie ein Recordset geöffnet haben, müssen Sie die Datensätze zum Anzeigen von Werten, den Zugriff auf Berechnungen ausführen, Berichte usw. Scrollen können, wenn Sie innerhalb des Recordsets von Datensatz zu Datensatz wechseln.  
  
 In diesem Thema wird Folgendes erläutert:  
  
-   [Gewusst wie: Bildlauf aus einem Datensatz in eine andere in einem Recordset](#_core_scrolling_from_one_record_to_another).  
  
-   [Unter welche Umständen Durchführen eines Bildlaufs ist, und wird nicht unterstützt](#_core_when_scrolling_is_supported).  
  
##  <a name="_core_scrolling_from_one_record_to_another"></a>Durchführen eines Bildlaufs aus einem Datensatz in eine andere  
 Klasse `CRecordset` bietet die **verschieben** Memberfunktionen zum Durchführen eines Bildlaufs in einem Recordset. Diese Funktionen verschieben den aktuellen Datensatz von Rowsets. Wenn Sie implementiert haben, gesammelte, eine **verschieben** Vorgang verschiebt das Recordset, indem Sie die Größe des Rowsets. Nicht implementiert, gesammelte, einen Aufruf einer **verschieben** Funktion verschiebt das Recordset von einem Datensatz jedes Mal. Weitere Informationen über das gesammelte finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
> [!NOTE]
>  Beim Verschieben von durch ein Recordset werden gelöschte Datensätze möglicherweise nicht übersprungen. Weitere Informationen finden Sie unter der [IsDeleted](../../mfc/reference/crecordset-class.md#isdeleted) Memberfunktion.  
  
 Zusätzlich zu den **verschieben** Funktionen `CRecordset` bietet Memberfunktionen zum Überprüfen, ob Sie über das Ende oder vor den Anfang des Recordsets gescrollt haben.  
  
 Um zu bestimmen, ob Scrollen im Recordset möglich ist, rufen die `CanScroll` Memberfunktion.  
  
#### <a name="to-scroll"></a>Um einen Bildlauf durchzuführen  
  
1.  Einen Datensatz oder ein Rowset vorwärts: Rufen Sie die [MoveNext](../../mfc/reference/crecordset-class.md#movenext) Memberfunktion.  
  
2.  Abwärtskompatibilität einen Datensatz oder ein Rowset: Rufen Sie die [MovePrev](../../mfc/reference/crecordset-class.md#moveprev) Memberfunktion.  
  
3.  Auf den ersten Eintrag in das Recordset: Rufen Sie die [MoveFirst](../../mfc/reference/crecordset-class.md#movefirst) Memberfunktion.  
  
4.  Der letzte Datensatz in das Recordset oder des letzten Rowsets: Rufen Sie die [MoveLast](../../mfc/reference/crecordset-class.md#movelast) Memberfunktion.  
  
5.  *N* Datensätze relativ zur aktuellen Position: Rufen Sie die [verschieben](../../mfc/reference/crecordset-class.md#move) Memberfunktion.  
  
#### <a name="to-test-for-the-end-or-the-beginning-of-the-recordset"></a>So testen Sie für das Ende oder am Anfang des Recordsets  
  
1.  Haben Sie hinter dem letzten Datensatz werden gescrollt? Rufen Sie die [IsEOF](../../mfc/reference/crecordset-class.md#iseof) Memberfunktion.  
  
2.  Haben Sie vor dem ersten Datensatz (rückwärts) werden gescrollt? Rufen Sie die [IsBOF](../../mfc/reference/crecordset-class.md#isbof) Memberfunktion.  
  
 Im folgenden Codebeispiel wird mit `IsBOF` und `IsEOF` die Grenzwerte eines Recordsets zu erkennen, wenn in beiden Richtungen Durchführen eines Bildlaufs.  
  
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
  
 `IsEOF`Gibt einen Wert ungleich NULL zurück, wenn das Recordset hinter dem letzten Datensatz positioniert ist. `IsBOF`Gibt einen Wert ungleich NULL zurück, wenn das Recordset, vor dem ersten Datensatz (vor allen Datensätzen positioniert ist). In beiden Fällen ist gibt es kein aktueller Datensatz, das verarbeitet werden. Beim Aufrufen `MovePrev` Wenn `IsBOF` ist bereits **"true"** , oder rufen Sie `MoveNext` Wenn `IsEOF` ist bereits **"true"**, löst das Framework eine `CDBException`. Sie können auch `IsBOF` und `IsEOF` für ein leeres Recordset zu überprüfen.  
  
 Weitere Informationen zur Recordsetnavigation finden Sie unter [Recordset: Lesezeichen und Absolute Positionen (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md).  
  
##  <a name="_core_when_scrolling_is_supported"></a>Beim Durchführen eines Bildlaufs unterstützt wird  
 Wie ursprünglich vorgesehen SQL bereitgestellten Bildlauf ausschließlich vorwärts ausgeführt, aber ODBC erweitert Durchführen eines Bildlaufs Funktionen. Das verfügbare Maß an Unterstützung für das Durchführen eines Bildlaufs hängt von der ODBC-Treiber, die Ihre Anwendung mit ODBC-API-Konformitätsgrad des Treibers arbeitet, und gibt an, ob die ODBC-Cursorbibliothek in den Arbeitsspeicher geladen wird. Weitere Informationen finden Sie unter [ODBC](../../data/odbc/odbc-basics.md) und [ODBC: die ODBC-Cursorbibliothek](../../data/odbc/odbc-the-odbc-cursor-library.md).  
  
> [!TIP]
>  Sie können steuern, ob die Cursorbibliothek verwendet wird. Finden Sie unter der `bUseCursorLib` und `dwOptions` Parameter [CDatabase:: Open](../../mfc/reference/cdatabase-class.md#open).  
  
> [!NOTE]
>  Im Gegensatz zu den MFC-DAO-Klassen, die MFC-ODBC-Klassen nicht bieten eine Reihe von **suchen** Funktionen für das Suchen des nächsten (oder vorherigen) Datensatzes, der erfüllt die Kriterien angegeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Recordset (ODBC)](../../data/odbc/recordset-odbc.md)   
 [CRecordset::CanScroll](../../mfc/reference/crecordset-class.md#canscroll)   
 [CRecordset::CheckRowsetError](../../mfc/reference/crecordset-class.md#checkrowseterror)   
 [Recordset: Filtern von Datensätzen (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)