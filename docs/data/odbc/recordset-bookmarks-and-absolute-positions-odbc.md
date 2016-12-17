---
title: "Recordset: Lesezeichen und absolute Positionen (ODBC)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "SetAbsolutePosition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Absolute Positionen, ODBC-Recordsets"
  - "Lesezeichen"
  - "Lesezeichen, CDBVariant"
  - "Lesezeichen, ODBC-Recordsets"
  - "CDBVariant-Klasse, Lesezeichen"
  - "Cursor [ODBC], Absolute Position in Recordsets"
  - "GetBookmark-Methode"
  - "ODBC-Recordsets, Absolute Positionen"
  - "ODBC-Recordsets, Lesezeichen"
  - "Positionieren von Datensätzen"
  - "Datensatzpositionierung"
  - "Recordsets, Absolute Positionen"
  - "Recordsets, Lesezeichen"
  - "SetAbsolutePosition-Methode"
  - "SetAbsolutePosition-Methode, Lesezeichen"
  - "SetBookmark-Methode"
ms.assetid: 189788d6-33c1-41c5-9265-97db2a5d43cc
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Recordset: Lesezeichen und absolute Positionen (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Thema bezieht sich auf die MFC\-ODBC\-Klassen.  
  
 Wenn Sie durch ein Recordset navigieren, benötigen Sie häufig die Möglichkeit, zu einem bestimmten Datensatz zurückzukehren.  Zwei Möglichkeiten hierfür bieten das Lesezeichen und die absolute Position eines Datensatzes.  
  
 In diesem Thema wird Folgendes erläutert:  
  
-   [Wie Sie Lesezeichen verwenden](#_core_bookmarks_in_mfc_odbc).  
  
-   [Wie Sie mithilfe der absoluten Position den aktuellen Datensatz festlegen](#_core_absolute_positions_in_mfc_odbc).  
  
##  <a name="_core_bookmarks_in_mfc_odbc"></a> Lesezeichen in MFC\-ODBC  
 Ein Lesezeichen identifiziert einen Datensatz eindeutig.  Wenn Sie durch ein Recordset navigieren, können Sie sich nicht immer auf die absolute Position eines Datensatzes verlassen, da Datensätze aus dem Recordset gelöscht werden können.  Zuverlässiger markieren Sie die Position eines Datensatzes mit dessen Lesezeichen.  Die `CRecordset`\-Klasse stellt Memberfunktionen für folgende Operationen bereit:  
  
-   Ermitteln des Lesezeichens für den aktuellen Datensatz, das Sie dann in einer Variablen speichern können \([GetBookmark](../Topic/CRecordset::GetBookmark.md)\).  
  
-   Schnelles Navigieren zu einem bestimmten Datensatz durch Angabe des Lesezeichens, das Sie in einer Variablen gespeichert hatten \([SetBookmark](../Topic/CRecordset::SetBookmark.md)\).  
  
 Das folgende Beispiel zeigt, wie Sie mithilfe dieser Memberfunktionen den aktuellen Datensatz markieren und später zu diesem zurückkehren können:  
  
```  
// rs is a CRecordset or  
// CRecordset-derived object  
  
CDBVariant varRecordToReturnTo;  
rs.GetBookmark( varRecordToReturnTo );  
  
// More code in which you  
// move to other records  
  
rs.SetBookmark( varRecordToReturnTo );  
```  
  
 Sie müssen aus dem [CDBVariant Class](../../mfc/reference/cdbvariant-class.md)\-Objekt nicht den zugrunde liegenden Datentyp extrahieren.  Weisen Sie der Variablen lediglich mit `GetBookmark` einen Wert zu und kehren Sie mit `SetBookmark` zu diesem Lesezeichen zurück.  
  
> [!NOTE]
>  Je nach dem verwendeten ODBC\-Treiber und dem Recordsettyp werden Lesezeichen eventuell nicht unterstützt.  Sie können problemlos feststellen, ob Lesezeichen unterstützt werden, indem Sie [CRecordset::CanBookmark](../Topic/CRecordset::CanBookmark.md) aufrufen.  Falls Lesezeichen unterstützt werden, müssen Sie explizit angeben, dass diese implementiert werden sollen. Übergeben Sie hierzu den Wert **CRecordset::useBookmarks** an die [CRecordset::Open](../Topic/CRecordset::Open.md)\-Memberfunktion.  Sie müssen außerdem nach bestimmten Recordset\-Operationen die Beständigkeit der Lesezeichen überprüfen.  Wenn Sie ein Recordset beispielsweise mit **Requery** neu abgefragt haben, sind die Lesezeichen unter Umständen nicht mehr gültig.  Rufen Sie [CDatabase::GetBookmarkPersistence](../Topic/CDatabase::GetBookmarkPersistence.md) auf, um zu überprüfen, ob Sie `SetBookmark` sicher aufrufen können.  
  
##  <a name="_core_absolute_positions_in_mfc_odbc"></a> Absolute Positionen in MFC\-ODBC  
 Neben Lesezeichen bietet die `CRecordset`\-Klasse die Möglichkeit, den aktuellen Datensatz durch Angabe einer Ordinalposition festzulegen.  Diese Methode wird als absolutes Positionieren bezeichnet.  
  
> [!NOTE]
>  Absolutes Positionieren ist in Vorwärts\-Recordsets nicht möglich.  Weitere Informationen über Vorwärts\-Recordsets finden Sie unter [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md).  
  
 Rufen Sie [CRecordset::SetAbsolutePosition](../Topic/CRecordset::SetAbsolutePosition.md) auf, um den Zeiger für den aktuellen Datensatz mithilfe einer absoluten Position zu verschieben.  Wenn Sie einen Wert an `SetAbsolutePosition` übergeben, wird der Datensatz zum aktuellen Datensatz, der dieser Ordinalposition zugeordnet ist.  
  
> [!NOTE]
>  Die absolute Position eines Datensatzes kann nicht immer zuverlässig angegeben werden.  Wenn der Benutzer Datensätze aus dem Recordset löscht, ändert sich die Ordinalposition aller nachfolgenden Datensätze.  Für das Bewegen des aktuellen Datensatzes werden daher Lesezeichen empfohlen.  Weitere Informationen finden Sie unter [Lesezeichen in MFC ODBC](#_core_bookmarks_in_mfc_odbc).  
  
 Weitere Informationen zur Recordsetnavigation finden Sie unter [Recordset: Scrollen \(ODBC\)](../../data/odbc/recordset-scrolling-odbc.md).  
  
## Siehe auch  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)