---
title: 'ODBC: Die ODBC-Cursorbibliothek | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- cursor library [ODBC]
- snapshots, support in ODBC
- timestamps, ODBC timestamp columns
- ODBC cursor library [ODBC]
- static cursors
- ODBC drivers, Level 1
- ODBC drivers, cursor support
- positioned updates
- cursors, ODBC cursor library
- Level 1 ODBC drivers
- cursor library [ODBC], snapshots
- ODBC, timestamp
- positioning cursors
ms.assetid: 6608db92-82b1-4164-bb08-78153c227be3
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3d849580ce3e9b264c854633c6bb9f274874c21d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="odbc-the-odbc-cursor-library"></a>ODBC: Die ODBC-Cursorbibliothek
In diesem Thema wird beschrieben, die ODBC-Cursorbibliothek und erläutert, ihn zu verwenden. Weitere Informationen finden Sie unter:  
  
-   [Cursorbibliothek und Level 1-ODBC-Treiber](#_core_the_cursor_library_and_level_1_odbc_drivers)  
  
-   [Positionierte Update- und Timestamp-Spalten](#_core_positioned_updates_and_timestamp_columns)  
  
-   [Verwenden die Cursorbibliothek](#_core_using_the_cursor_library)  
  
 Der ODBC-Cursorbibliothek ist eine Dynamic Link Library (DLL), die zwischen der ODBC-Treiber-Manager und der Treiber befindet. In ODBC-Begriffen ausgedrückt unterhält der Treiber einen Cursor zum Nachverfolgen seiner Position im Recordset. Der Cursor markiert die Position in das Recordset, Sie haben bereits ein Bildlauf durchgeführt, den aktuellen Datensatz.  
  
##  <a name="_core_the_cursor_library_and_level_1_odbc_drivers"></a>Cursorbibliothek und Level 1-ODBC-Treiber  
 Der ODBC-Cursorbibliothek bietet Level 1-Treiber die folgenden neuen Funktionen:  
  
-   Vorwärts und rückwärts scrollen. Ebene-2-Treiber ist nicht die Cursorbibliothek erforderlich, da sie bereits bildlauffähig sind.  
  
-   Unterstützung für Momentaufnahmen. Die Cursorbibliothek verwaltet einen Puffer, der die Momentaufnahme Datensätze enthält. Dieser Puffer spiegelt wider, Lösch- und Bearbeitungen Datensätze jedoch nicht die Ergänzungen, löschungen oder Änderungen von anderen Benutzern des Programms. Aus diesem Grund ist die Momentaufnahme nur so aktuell wie die Cursorbibliothek Puffer. Der Puffer auch reflektiert keinen eigenen Ergänzungen bis zum Aufruf von **Requery**. Dynasets verwenden Sie die Cursorbibliothek nicht.  
  
 Die Cursorbibliothek bietet Ihnen Momentaufnahmen (statische Cursor), auch wenn sie vom Treiber nicht unterstützt werden. Wenn der Treiber bereits statische Cursor unterstützt, müssen Sie nicht beim Laden der Cursorbibliothek, um Unterstützung zu erhalten. Wenn Sie die Cursorbibliothek verwenden, können Sie nur Momentaufnahmen und Forward-only-Recordsets verwenden. Wenn der Treiber Dynasets (KEYSET_DRIVEN Cursor unterstützt) und verwendet werden sollen, müssen Sie die Cursorbibliothek nicht verwenden. Wenn Sie Momentaufnahmen und Dynasets verwenden möchten, müssen Sie diese auf zwei unterschiedlichen Grundlage `CDatabase` Objekte (zwei unterschiedliche Verbindungen), wenn der Treiber beide unterstützt.  
  
##  <a name="_core_positioned_updates_and_timestamp_columns"></a>Positionierte Update- und Timestamp-Spalten  
  
> [!NOTE]
>  Auf ODBC-Datenquellen können Sie über die MFC-ODBC-Klassen zugreifen, wie in diesem Thema beschrieben, oder über die MFC-Datenzugriffsobjekt-Klassen (DAO-Klassen).  
  
> [!NOTE]
>  Wenn der ODBC-Treiber unterstützt **SQLSetPos**, MFC verwendet, falls verfügbar, wird dieses Thema gilt nicht für Sie.  
  
 Positionierte Updates werden von den meisten Level 1-Treiber nicht unterstützt. Solche Treiber abhängig von der Cursorbibliothek in dieser Hinsicht emuliert die Funktionen der Level 2-Treiber ab. Die Cursorbibliothek emuliert positioniertes Update unterstützen, indem Sie ein gesuchtes Update auf die unveränderliche Felder.  
  
 In einigen Fällen kann ein Recordset eine Timestamp-Spalte als eines dieser unveränderlichen Felder enthalten. In MFC-Recordsets mit Tabellen, die Timestamp-Spalten enthalten zwei Aspekte zu beachten.  
  
 Das erste Problem betrifft mit aktualisierbaren Momentaufnahmen für Tabellen mit Timestamp-Spalten. Wenn die Tabelle, die an die die Momentaufnahme gebunden ist eine Timestamp-Spalte enthält, sollten Sie aufrufen **Requery** nach dem Aufruf **bearbeiten** und **Update**. Wenn dies nicht der Fall ist, wird Sie möglicherweise nicht den gleichen Datensatz erneut bearbeiten. Beim Aufruf **bearbeiten** und dann **Update**, wird der Datensatz mit der Datenquelle geschrieben, und die Timestamp-Spalte wird aktualisiert. Wenn Sie nicht aufrufen **Requery**, Timestamp-Wert für den Datensatz in der Momentaufnahme nicht mehr mit dem entsprechenden Timestamp in der Datenquelle überein. Wenn Sie versuchen, den Datensatz erneut aktualisieren, kann die Datenquelle des Updates aufgrund des Konflikts unterbinden.  
  
 Das zweite Problem betrifft die Einschränkungen der Klasse [CTime](../../atl-mfc-shared/reference/ctime-class.md) bei Verwendung mit der `RFX_Date` Funktion Datum und die Daten in oder aus einer Tabelle zu übertragen. Verarbeitung der `CTime` -Objekts erzwingt ein gewisser Aufwand in Form von zusätzlichen intermediate Verarbeitung während der Datenübertragung. Der Datumsbereich `CTime` Objekte möglicherweise für einige Anwendungen auch zu beschränken. Eine neue Version von den `RFX_Date` Funktion nimmt einen ODBC **TIMESTAMP_STRUCT** Parameter anstelle von einer `CTime` Objekt. Weitere Informationen finden Sie unter `RFX_Date` in [Makros und Globals](../../mfc/reference/mfc-macros-and-globals.md) in der *MFC-Referenz*.  

  
##  <a name="_core_using_the_cursor_library"></a>Verwenden die Cursorbibliothek  
 Wenn Sie mit einer Datenquelle verbinden – durch den Aufruf [CDatabase:: OpenEx](../../mfc/reference/cdatabase-class.md#openex) oder [CDatabase:: Open](../../mfc/reference/cdatabase-class.md#open) – Sie können angeben, ob die Cursorbibliothek für die Datenquelle verwendet. Wenn Sie Momentaufnahmen von dieser Datenquelle erstellen, geben Sie die **dwOptions** -Option in der `dwOptions` Parameter `OpenEx` , oder geben Sie **"true"** für die  **bUseCursorLib** Parameter **öffnen** (der Standardwert ist **"true"**). Wenn der ODBC-Treiber Dynasets unterstützt und Dynasets für die Datenquelle öffnen möchten, verwenden Sie nicht die Cursorbibliothek (es maskiert einige Funktionalität des Treibers für Dynasets erforderlich). Geben Sie in diesem Fall nicht **dwOptions** in `OpenEx` , oder geben Sie **"false"** für die **bUseCursorLib** im Parameters **Öffnen**.  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlagen zu ODBC](../../data/odbc/odbc-basics.md)