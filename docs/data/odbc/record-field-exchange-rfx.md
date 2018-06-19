---
title: Datensatzfeldaustausch (RFX) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- RFX (ODBC) [C++]
- data [MFC], moving between sources and recordsets
- database classes [C++], RFX
- data [MFC]
- ODBC [C++], RFX
ms.assetid: f5ddfbf0-2901-48d7-9848-4fb84de3c7ee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8b214cf05115056efc96c4a078dedd4b7f9a3a1a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33091653"
---
# <a name="record-field-exchange-rfx"></a>Datensatzfeldaustausch (RFX)
Die MFC-ODBC-Datenbankklassen automatisieren, Verschieben von Daten zwischen der Datenquelle und einem [Recordset](../../data/odbc/recordset-odbc.md) Objekt. Beim Ableiten einer Klasse von [CRecordset](../../mfc/reference/crecordset-class.md) und Abrufens von Zeilen nicht verwenden, werden Daten durch die Datensatzfeldaustausch (RFX)-Mechanismus übertragen.  
  
> [!NOTE]
>  Wenn Sie das gesammelte Abrufen von Zeilen in einer abgeleiteten implementiert haben `CRecordset` -Klasse, verwendet das Framework das Massenkopieren Datensatzfeldaustausch (Bulk-RFX)-Mechanismus zum Übertragen von Daten. Weitere Informationen finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 RFX ähnelt Dialogdatenaustausch (DDX). Verschieben von Daten zwischen einer Datenquelle und den Felddatenmembern eines Recordset-Objekts erfordert mehrere Aufrufe des Recordsets [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) und beträchtliche Interaktion zwischen dem Framework und [ODBC](../../data/odbc/odbc-basics.md). Der RFX-Mechanismus ist typsicher und erspart Ihnen das Aufrufen von ODBC-Funktionen wie z. B. **:: SQLBindCol**. Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
 RFX ist hauptsächlich für Sie transparent. Wenn Sie mit der MFC-Anwendungs-Assistenten die Recordset-Klassen deklarieren oder **Klasse hinzufügen** (wie in beschrieben [Hinzufügen eines MFC-ODBC-Consumers](../../mfc/reference/adding-an-mfc-odbc-consumer.md)), RFX hineinkopieren automatisch erstellt wird. Recordset-Klasse muss von der Basisklasse abgeleitet werden `CRecordset` vom Framework bereitgestellt. MFC-Anwendung-Assistenten können Sie eine anfängliche Recordsetklasse zu erstellen. **Fügen Sie Klasse** können Sie die anderen Recordset-Klassen hinzufügen, wenn Sie sie benötigen. Weitere Informationen und Beispiele finden Sie unter [Hinzufügen eines MFC-ODBC-Consumers](../../mfc/reference/adding-an-mfc-odbc-consumer.md).  
  
 Wenn Sie möchten, müssen Sie manuell eine kleine Menge von RFX-Code in drei Fällen hinzufügen:  
  
-   Verwenden Sie parametrisierte Abfragen. Weitere Informationen finden Sie unter [Recordset: Parametrisieren eines Recordsets (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).  
  
-   Führen Sie Joins (mit einem Recordset für Spalten aus zwei oder mehr Tabellen aus). Weitere Informationen finden Sie unter [Recordset: Ausführen einer Verknüpfung (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md).  
  
-   Binden Sie Datenspalten dynamisch. Dies ist weniger gebräuchlich als Parametrisierung. Weitere Informationen finden Sie unter [Recordset: Dynamisches Binden von Spalten (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).  
  
 Wenn Sie einen tieferen Kenntnissen der RFX benötigen, finden Sie unter [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 In den folgenden Themen wird erläutert, die Details der Verwendung des Recordset-Objekte:  
  
-   [Datensatzfeldaustausch: Verwenden von RFX](../../data/odbc/record-field-exchange-using-rfx.md)  
  
-   [Datensatzfeldaustausch: Verwenden der RFX-Funktionen](../../data/odbc/record-field-exchange-using-the-rfx-functions.md)  
  
-   [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Open Sie Database Connectivity (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)   
 [Recordset (ODBC)](../../data/odbc/recordset-odbc.md)   
 [MFC-ODBC-nutzen](../../mfc/reference/adding-an-mfc-odbc-consumer.md)   
 [Datenbankunterstützung, MFC-Anwendung-Assistent](../../mfc/reference/database-support-mfc-application-wizard.md)   
 [CRecordset-Klasse](../../mfc/reference/crecordset-class.md)