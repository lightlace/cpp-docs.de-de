---
title: 'Recordset: Lesezeichen und Absolute Positionen (ODBC) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- SetAbsolutePosition
dev_langs:
- C++
helpviewer_keywords:
- CDBVariant class, bookmarks
- absolute positions, ODBC recordsets
- bookmarks, CDBVariant
- bookmarks, ODBC recordsets
- ODBC recordsets, absolute positions
- ODBC recordsets, bookmarks
- cursors [ODBC], absolute position in recordsets
- recordsets, bookmarks
- bookmarks
- SetAbsolutePosition method
- recordsets, absolute positions
- positioning records
- SetBookmark method
- record positioning
- GetBookmark method
- SetAbsolutePosition method, bookmarks
ms.assetid: 189788d6-33c1-41c5-9265-97db2a5d43cc
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4b206e5d09d86613af0585df7510b0f88397984a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="recordset-bookmarks-and-absolute-positions-odbc"></a>Recordset: Lesezeichen und absolute Positionen (ODBC)
Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.  
  
 Wenn Sie über ein Recordset navigieren, benötigen Sie häufig eine Möglichkeit, zu einem bestimmten Datensatz zurückgeben. Ein Datensatz Lesezeichen und absolute Position bieten zwei solche Methoden.  
  
 In diesem Thema wird Folgendes erläutert:  
  
-   [Verwendung von Lesezeichen](#_core_bookmarks_in_mfc_odbc).  
  
-   [Zum Festlegen des aktuellen Datensatzes mit absolute Positionen](#_core_absolute_positions_in_mfc_odbc).  
  
##  <a name="_core_bookmarks_in_mfc_odbc"></a>Lesezeichen in MFC-ODBC  
 Ein Lesezeichen identifiziert einen Datensatz eindeutig. Wenn Sie über ein Recordset navigieren, können nicht Sie immer auf die absolute Position eines Datensatzes basieren, da Datensätze aus dem Recordset gelöscht werden können. Die zuverlässige Möglichkeit zum Nachverfolgen die Position eines Datensatzes ist die Verwendung des Lesezeichens. Klasse `CRecordset` stellt Memberfunktionen zur:  
  
-   Das Lesezeichen des aktuellen Datensatzes abrufen, damit Sie es in einer Variablen speichern können ([GetBookmark](../../mfc/reference/crecordset-class.md#getbookmark)).  
  
-   Verschieben schnell zu einem bestimmten Datensatz durch Angabe des Lesezeichens, das Sie zuvor in einer Variablen gespeichert ([SetBookmark](../../mfc/reference/crecordset-class.md#setbookmark)).  
  
 Das folgende Beispiel zeigt, wie diese Memberfunktionen auf den aktuellen Datensatz markieren und sie später zurückkehren:  
  
```  
// rs is a CRecordset or  
// CRecordset-derived object  
  
CDBVariant varRecordToReturnTo;  
rs.GetBookmark( varRecordToReturnTo );  
  
// More code in which you  
// move to other records  
  
rs.SetBookmark( varRecordToReturnTo );  
```  
  
 Sie müssen nicht aus den zugrunde liegenden Datentyp extrahieren der [CDBVariant-Klasse](../../mfc/reference/cdbvariant-class.md) Objekt. Weisen Sie den Wert mit `GetBookmark` und zurück zu diesem Lesezeichen mit `SetBookmark`.  
  
> [!NOTE]
>  Je nach ODBC-Treiber und Recordsettyp werden Lesezeichen möglicherweise nicht unterstützt. Sie können problemlos feststellen, ob Lesezeichen, durch den Aufruf unterstützt werden [CRecordset:: CanBookmark](../../mfc/reference/crecordset-class.md#canbookmark). Darüber hinaus Lesezeichen unterstützt, Sie müssen explizit auswählen, implementieren Sie diese durch Angabe der **CRecordset:: useBookmarks** -Option in der [CRecordset](../../mfc/reference/crecordset-class.md#open) Memberfunktion. Sie sollten auch die Beibehaltung von Lesezeichen nach bestimmten Vorgängen Recordset überprüfen. Beispielsweise, wenn Sie **Requery** ein Recordset Lesezeichen möglicherweise nicht mehr gültig sein. Rufen Sie [CDatabase:: GetBookmarkPersistence](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) zu überprüfen, ob Sie sicher aufrufen können `SetBookmark`.  
  
##  <a name="_core_absolute_positions_in_mfc_odbc"></a>Absolute Positionen in MFC-ODBC  
 Neben Lesezeichen-Klasse `CRecordset` können Sie den aktuellen Datensatz festgelegt wird, indem Sie eine Ordnungsposition. Dies wird als absolute Positionierung bezeichnet.  
  
> [!NOTE]
>  Es ist nicht verfügbar, auf die Forward-only-Recordsets, absolute Positionierung. Weitere Informationen zu Forward-only-Recordsets, finden Sie unter [Recordset (ODBC)](../../data/odbc/recordset-odbc.md).  
  
 Aufrufen, um den Zeiger für den aktuellen Datensatz verwendet absolute Position zu verschieben, [CRecordset:: SetAbsolutePosition auf](../../mfc/reference/crecordset-class.md#setabsoluteposition). Wenn Sie einen Wert zu übergeben `SetAbsolutePosition`des Datensatzes für die Ordnungsposition der aktuelle Datensatz wie folgt aussieht.  
  
> [!NOTE]
>  Die absolute Position eines Datensatzes ist möglicherweise unzuverlässig. Wenn der Benutzer die Datensätze aus dem Recordset, der die Ordnungsposition der nachfolgende Datensatz Änderungen löscht. Lesezeichen sind die empfohlene Methode zum Verschieben von des aktuellen Datensatzes. Weitere Informationen finden Sie unter [Lesezeichen in MFC ODBC](#_core_bookmarks_in_mfc_odbc).  
  
 Weitere Informationen zur Recordsetnavigation finden Sie unter [Recordset: Scrollen (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Recordset (ODBC)](../../data/odbc/recordset-odbc.md)