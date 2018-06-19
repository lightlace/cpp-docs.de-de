---
title: 'Recordset: Erneutes Abfragen eines Recordsets (ODBC) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- recordsets, requerying
- requerying recordsets
- Requery method
- ODBC recordsets, requerying
- refreshing recordsets
ms.assetid: 4ebc3b5b-5b91-4f51-a967-245223c6b8e1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a3157f416cf6fb7e0fd3b5ad4797b83de218c9ef
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33091576"
---
# <a name="recordset-requerying-a-recordset-odbc"></a>Recordset: Erneutes Abfragen eines Recordsets (ODBC)
Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.  
  
 In diesem Thema wird erläutert, wie Sie einem Recordset-Objekt verwenden können, um requery (d. h. aktualisieren) selbst aus der Datenbank, und wenn Sie möchten, dass bei der [Requery](../../mfc/reference/crecordset-class.md#requery) Memberfunktion.  
  
 Die Hauptgründe für erneutes Abfragen eines Recordsets sind:  
  
-   Schalten Sie das Recordset, das auf dem neuesten Stand in Bezug auf die von Ihnen oder von anderen Benutzern hinzugefügt und Datensätze, die von anderen Benutzern (diejenigen, die Sie löschen, sind bereits im Recordset widergespiegelt) gelöscht.  
  
-   Aktualisieren Sie das Recordset basierend auf Parameterwerte zu ändern.  
  
##  <a name="_core_bringing_the_recordset_up_to_date"></a> Aktualisieren des Recordsets bis Datum  
 In vielen Fällen möchten Sie das Recordset-Objekt, um ihn zu schalten requery auf dem neuesten Stand. In einer Umgebung Mehrbenutzer-Datenbank können anderen Benutzern während der Lebensdauer des Recordsets Änderungen an den Daten vornehmen. Weitere Informationen zu Wenn Recordset von anderen Benutzern vorgenommene Änderungen wiedergibt, und wenn Recordsets anderer Benutzer die Änderung zu reflektieren, finden Sie unter [Recordset: wie Recordsets Update Datensätzen (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md) und [Dynaset](../../data/odbc/dynaset.md).  
  
##  <a name="_core_requerying_based_on_new_parameters"></a> Erneutes Abfragen basierend auf neuen Parametern  
 Eine andere häufige – und ebenso wichtig – verwenden der [Requery](../../mfc/reference/crecordset-class.md#requery) entspricht, wählen Sie einen neuen Satz von Datensätzen auf Grundlage der Parameterwerte zu ändern.  
  
> [!TIP]
>  Geschwindigkeit der Abfrage ist wahrscheinlich wesentlich schneller, wenn Sie aufrufen **Requery** veränderlichen Parameterwerte als, wenn Sie aufrufen **öffnen** erneut aus.  
  
##  <a name="_core_requerying_dynasets_vs.._snapshots"></a> Erneutes Abfragen Dynasets Vs aus. Momentaufnahmen  
 Da Dynasets vorgesehen sind, um eine Gruppe von Datensätzen mit dynamischen auf dem neuesten Stand Daten darzustellen, möchten Sie Dynasets requery häufig, wenn andere Benutzer den Ergänzungen widerspiegeln werden sollen. Momentaufnahmen sind hingegen, hilfreich, da Sie problemlos auf ihren statischen Inhalten verlassen können, während Sie Berichte vorbereiten, Berechnen von Summen und so weiter. Weiterhin, sollten Sie in einigen Fällen auch eine Momentaufnahme erneut abgefragt. In einer mehrbenutzerumgebung können momentaufnahmedaten Synchronisierung mit der Datenquelle verloren gehen als anderer Benutzer die Datenbank zu ändern.  
  
#### <a name="to-requery-a-recordset-object"></a>Um einem Recordset-Objekt zu aktualisieren.  
  
1.  Rufen Sie die [Requery](../../mfc/reference/crecordset-class.md#requery) -Memberfunktion des Objekts.  
  
 Alternativ können Sie schließen und öffnen das ursprüngliche Recordset. In beiden Fällen stellt die neue Recordset den aktuellen Status der Datenquelle dar.  
  
 Ein Beispiel finden Sie unter [Datensatzansichten: Füllen eines Listenfelds aus einem zweiten Recordset](../../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md).  
  
> [!TIP]
>  Zur Optimierung **Requery** Leistung zu erzielen, sollten nicht ändern, des Recordsets [Filter](../../data/odbc/recordset-filtering-records-odbc.md) oder [sortieren](../../data/odbc/recordset-sorting-records-odbc.md). Ändern Sie nur den Parameterwert vor dem Aufruf **Requery**.  
  
 Wenn die **Requery** rufen ein Fehler auftritt, können Sie den Aufruf wiederholen; andernfalls, die Anwendung beendet werden sollen, ordnungsgemäß. Ein Aufruf von **Requery** oder **öffnen** für eine beliebige Anzahl von Gründen fehlschlagen. Möglicherweise tritt ein Netzwerkfehler aufgetreten. oder während des Aufrufs, nachdem die vorhandenen Daten freigegeben sind, aber bevor die neuen Daten abgerufen werden, ein anderer Benutzer erhalten möglicherweise exklusiven Zugriff; oder die Tabelle Recordset abhängt gelöscht werden konnte.  
  
## <a name="see-also"></a>Siehe auch  
 [Recordset (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Recordset: Dynamisches Binden von Datenspalten (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)   
 [Recordset: Erstellen und Schließen von Recordsets (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)