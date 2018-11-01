---
title: 'Datensatzfeldaustausch: Verwenden von RFX'
ms.date: 11/04/2016
helpviewer_keywords:
- RFX (ODBC), implementing
ms.assetid: ada8f043-37e6-4d41-9db3-92c997a61957
ms.openlocfilehash: e1ecb43226c9e21f3b13c2d5b7c2a0f93b72f3cc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50469549"
---
# <a name="record-field-exchange-using-rfx"></a>Datensatzfeldaustausch: Verwenden von RFX

In diesem Thema wird erläutert, was Sie tun, um RFX zu verwenden wie das Framework ermöglicht.

> [!NOTE]
>  Dieses Thema gilt für Klassen, die von [CRecordset](../../mfc/reference/crecordset-class.md) in denen das gesammelte Abrufen von Zeilen nicht implementiert wurde. Wenn Sie gesammelte verwenden, wird die Massen-Datensatzfeldaustausch (Bulk-RFX) implementiert. Bulk RFX ähnelt RFX. Informationen zu den Unterschieden finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Die folgenden Themen enthalten Informationen an:

- [Datensatzfeldaustausch: Arbeiten mit Assistenten-Code](../../data/odbc/record-field-exchange-working-with-the-wizard-code.md) stellt die wichtigsten Komponenten von RFX vor und erläutert den Code, den MFS-Anwendungsassistenten und **Klasse hinzufügen** (siehe [Hinzufügen eines MFC-ODBC-Consumers ](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) schreiben, die zur Unterstützung von RFX und wie Sie den assistentencode nicht ändern möchten.

- [Datensatzfeldaustausch: Verwenden der RFX-Funktionen](../../data/odbc/record-field-exchange-using-the-rfx-functions.md) wird erläutert, wie Sie in der RFX-Funktionen in Aufrufen Ihrer `DoFieldExchange` außer Kraft setzen.

Die folgende Tabelle zeigt Ihre Rolle in Bezug auf die Framework für Sie ausführt.

### <a name="using-rfx-you-and-the-framework"></a>Verwenden von RFX: Sie und das Framework

|Benutzer|Das Framework|
|---------|-------------------|

| Deklarieren Sie die Recordset-Klassen, mit einem Assistenten. Geben Sie Namen und Datentypen der Felddatenmember. | Der Assistent leitet eine `CRecordset` -Klasse und schreibt eine [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) für Sie zu überschreiben, die einen RFX für jedes felddatenelement Funktionsaufruf. | | () Optional) fügen Sie ggf. die erforderlichen Parameterdatenmember der Klasse manuell hinzu. RFX-Funktion, manuell hinzufügen `DoFieldExchange` für jeden Member des-Parameters Daten, fügen Sie einen Aufruf von [CFieldExchange::](../../mfc/reference/cfieldexchange-class.md#setfieldtype) für die Gruppe von Parametern, und geben Sie die Gesamtzahl von Parametern in [M_nParams ](../../mfc/reference/crecordset-class.md#m_nparams). Finden Sie unter [Recordset: Parametrisieren eines Recordsets (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md). || | () Optional) weitere Spalten manuell Felddatenmembern zu binden. Inkrementiert manuell [M_nFields](../../mfc/reference/crecordset-class.md#m_nfields). Finden Sie unter [Recordset: Dynamisches Binden von Datenspalten (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md). ||

| Erstellen Sie ein Objekt des Recordset-Klasse. Vor der Verwendung des Objekts an, legen Sie die Werte des Parameters Datenmember, sofern vorhanden. | Aus Effizienzgründen Vorbindung die Parameter, die mithilfe von ODBC. Wenn Sie Parameterwerte übergeben, wird Sie in das Framework an die Datenquelle übergeben. Nur die Parameterwerte zur Neuabfragen, weitergeleitet werden, es sei denn, die Zeichenfolgen sortieren und/oder die Filterung geändert haben. | | Öffnen Sie ein Recordset-Objekt mit [CRecordset:: Open](../../mfc/reference/crecordset-class.md#open). | Führt die Abfrage des Recordsets, bindet Spalten an Felddatenmember der Recordset und Aufrufe `DoFieldExchange` Datenaustausch zwischen dem ersten ausgewählten Datensatz und dem Recordset Felddatenmembern. | | Blättern Sie in das Recordset mit [CRecordset](../../mfc/reference/crecordset-class.md#move) oder einen Befehl im Menü oder Symbolleiste. | Aufrufe `DoFieldExchange` zum Übertragen von Daten aus der neuen aktuellen Datensatz, um den Felddatenmembern. | | Hinzufügen, aktualisieren und Löschen von Datensätzen. | Aufrufe `DoFieldExchange` zum Übertragen von Daten mit der Datenquelle. |

## <a name="see-also"></a>Siehe auch

[Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md)<br/>
[Recordset: Abrufen von Summen und anderen Aggregatergebnissen (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)<br/>
[CRecordset-Klasse](../../mfc/reference/crecordset-class.md)<br/>
[CFieldExchange-Klasse](../../mfc/reference/cfieldexchange-class.md)<br/>
[Makros, globale Funktionen und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)

