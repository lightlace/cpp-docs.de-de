---
title: 'Datensatzfeldaustausch: Verwenden von RFX | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- RFX (ODBC), implementing
ms.assetid: ada8f043-37e6-4d41-9db3-92c997a61957
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 296ae2e4f535e08924a77b8726b93778a6da5026
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="record-field-exchange-using-rfx"></a>Datensatzfeldaustausch: Verwenden von RFX
In diesem Thema wird erläutert, was Sie tun, um RFX in Bezug auf, was bewirkt, dass das Framework verwenden.  
  
> [!NOTE]
>  Dieses Thema bezieht sich auf von abgeleiteten Klassen [CRecordset](../../mfc/reference/crecordset-class.md) in denen der gesammelte Abrufen von Zeilen nicht implementiert wurde. Wenn Sie gesammelte verwenden, wird der Massen-Datensatzfeldaustausch (Bulk-RFX) implementiert. Bulk RFX ähnelt RFX. Um die Unterschiede zu verstehen, finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Die folgenden Themen enthalten Informationen an:  
  
-   [Datensatzfeldaustausch: Arbeiten mit Assistenten-Code](../../data/odbc/record-field-exchange-working-with-the-wizard-code.md) führt die Hauptkomponenten von RFX und erklärt, den Code, der MFC-Anwendung-Assistent und **Klasse hinzufügen** (wie in beschrieben [Hinzufügen eines MFC-ODBC-Consumers ](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) schreiben, die zur Unterstützung von RFX und wie Sie den assistentencode ändern möchten.  
  
-   [Datensatzfeldaustausch: Verwenden der RFX-Funktionen](../../data/odbc/record-field-exchange-using-the-rfx-functions.md) erläutert das Schreiben von Aufrufen der RFX-Funktionen in Ihrer `DoFieldExchange` außer Kraft setzen.  
  
 Die folgende Tabelle zeigt die Rolle in Bezug auf die Frameworks.  
  
### <a name="using-rfx-you-and-the-framework"></a>Verwenden von RFX: Sie und das Framework  
  
|Benutzer|Das Framework|  
|---------|-------------------|  

| Deklarieren Sie die Recordset-Klassen, mit einem Assistenten. Geben Sie Namen und Datentypen der Felddatenmember. | Der Assistent leitet ein `CRecordset` Klasse und schreibt eine [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) Außerkraftsetzung für Sie, einen RFX-Funktionsaufruf für jedes felddatenelement. |  
| (Optional) Alle erforderlichen Parameterdatenmember manuell der Klasse hinzufügen. RFX-Funktion, manuell hinzufügen `DoFieldExchange` für jedes Datenelement Parameter fügen Sie einen Aufruf von [CFieldExchange::](../../mfc/reference/cfieldexchange-class.md#setfieldtype) für die Gruppe der Parameter, und geben Sie die Gesamtanzahl von Parametern in [M_nParams ](../../mfc/reference/crecordset-class.md#m_nparams). Finden Sie unter [Recordset: Parametrisieren eines Recordsets (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md). ||  
| (Optional) Zusätzliche Spalten manuell Felddatenmembern zu binden. Inkrementiert manuell [M_nFields](../../mfc/reference/crecordset-class.md#m_nfields). Finden Sie unter [Recordset: Dynamisches Binden von Datenspalten (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md). ||  

| Erstellen Sie ein Objekt der Recordset-Klasse. Vor der Verwendung des Objekts an, legen Sie die Werte des Parameters Datenmember, sofern vorhanden. | Aus Effizienzgründen Vorbindung die Parameter, die mithilfe von ODBC. Wenn Sie Parameterwerte übergeben, übergibt das Framework sie mit der Datenquelle an. Wenn die Sortierung und/oder die Filterung Zeichenfolgen geändert haben, werden nur die Parameterwerte für Neuabfragen, gesendet. |  
| Öffnen Sie ein Recordset-Objekt mit [CRecordset](../../mfc/reference/crecordset-class.md#open). | Führt die Abfrage des Recordsets, bindet Spalten an Felddatenmember der Recordset und Aufrufe `DoFieldExchange` zum Austauschen von Daten zwischen dem ersten ausgewählten Datensatz und das Recordset-Felddatenmember. |  
| Blättern Sie in den Recordset mithilfe [CRecordset](../../mfc/reference/crecordset-class.md#move) oder einen Befehl im Menü oder auf der Symbolleiste. | Aufrufe `DoFieldExchange` zur Datenübertragung an den Felddatenmembern aus der neuen aktuellen Datensatz. |  
| Hinzufügen, aktualisieren und Löschen von Datensätzen. | Aufrufe `DoFieldExchange` zur Datenübertragung an die Datenquelle. |  
  
## <a name="see-also"></a>Siehe auch  
 [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md)   
 [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md)   
 [Recordset: Abrufen von Summen und anderen Aggregatergebnissen (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)   
 [CRecordset-Klasse](../../mfc/reference/crecordset-class.md)   
 [CDBException-Klasse](../../mfc/reference/cfieldexchange-class.md)   
 [Makros, globale Funktionen und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)

