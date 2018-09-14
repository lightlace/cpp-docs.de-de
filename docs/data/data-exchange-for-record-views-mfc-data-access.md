---
title: Datenaustausch für Datensatzansichten (MFC-Datenzugriff) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- RFX (record field exchange), data exchange mechanism
- RFX (record field exchange), record views
- record views, data exchange
- DDX (dialog data exchange), record views
- RFX (record field exchange)
ms.assetid: abc52ca7-6997-47a7-98f3-f347f52b1f72
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 58bda2d9a712e38951b8201c08e5bbbe369537eb
ms.sourcegitcommit: 6e479e33e8fd8e30ea32801edbff2e3415f31bf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2018
ms.locfileid: "33089414"
---
# <a name="data-exchange-for-record-views---mfc-data-access"></a>Datenaustausch für Datensatzansichten (MFC-Datenzugriff)
Bei Verwendung von [Klasse hinzufügen](../mfc/reference/adding-an-mfc-odbc-consumer.md) um die Steuerelemente in der Dialogfeldvorlagen-Ressource einer Datensatzansicht den Feldern eines Recordsets zuzuordnen, verwaltet das Framework den Datenaustausch in beide Richtungen – vom Recordset zu den Steuerelementen und umgekehrt. Wenn Sie den DDX-Mechanismus verwenden, müssen Sie den Code zur Datenübertragung nicht selbst schreiben.  
  
 DDX für Datensatzansichten funktioniert in Verbindung mit [RFX](../data/odbc/record-field-exchange-rfx.md) für Recordsets der Klasse `CRecordset` (ODBC).  RFX verschiebt Daten zwischen den aktuellen Datensatz der Datenquelle und den Felddatenmembern eines Recordset-Objekts. DDX verschiebt die Daten aus den Felddatenmembern in die Steuerelemente im Formular. Durch diese Kombination werden die Steuerelemente des Formulars am Anfang und immer dann gefüllt, wenn der Benutzer sich von Datensatz zu Datensatz bewegt. Zudem können aktualisierte Daten zurück in das Recordset und anschließend in die Datenquelle verschoben werden.  
  
 Die folgende Abbildung zeigt die Beziehung zwischen DDX und RFX für Datensatzansichten.  
  
 ![Dialogfeld&#45;Datenaustausch und eines Eintrags&#45;Feld Exchange](../data/media/vc37xt1.gif "vc37xt1")  
Dialogdatenaustausch und Datensatzfeldaustausch  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und Validierung](../mfc/dialog-data-exchange-and-validation.md). Weitere Informationen über RFX finden Sie unter [Datensatzfeldaustausch (RFX)](../data/odbc/record-field-exchange-rfx.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Datensatzansichten (MFC-Datenzugriff)](../data/record-views-mfc-data-access.md)   
 [Liste der ODBC-Treiber](../data/odbc/odbc-driver-list.md)