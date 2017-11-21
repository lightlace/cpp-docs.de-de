---
title: Anzeigen und Bearbeiten von Daten in einem Formular | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- forms [C++], displaying data
- displaying data [C++], forms
- ODBC [C++], forms
- record views [C++], displaying data
- data [MFC]
- data [MFC], displaying in a form
ms.assetid: c56185c4-12cb-40b1-b499-02b29ea83e3a
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: eb286e837d06ca12ebffa22d15ff9c534d815e83
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="displaying-and-manipulating-data-in-a-form"></a>Anzeigen und Verändern von Daten in einem Formular
Viele formularbasierten datenzugriffsanwendungen Daten auswählen und in den Feldern in einem Formular angezeigt wird. Die Datenbankklasse [CRecordView](../../mfc/reference/crecordview-class.md) bietet Ihnen eine [CFormView](../../mfc/reference/cformview-class.md) Objekt direkt mit einem Recordset-Objekt verbunden. Verwendet die Datensatzansicht [Dialogdatenaustausch (DDX)](../../mfc/dialog-data-exchange-and-validation.md) so verschieben Sie die Werte der Felder des aktuellen Datensatzes vom Recordset für die Steuerelemente im Formular und aktualisierte Informationen wieder auf das Recordset zu verschieben. Das Recordset verwendet wiederum Datensatzfeldaustausch (RFX) zum Verschieben von Daten zwischen der Felddatenmember und den entsprechenden Spalten in einer Tabelle in der Datenquelle.  
  
 Können Sie den Assistenten zum MFC-Anwendungen oder **Klasse hinzufügen** (wie in beschrieben [Hinzufügen eines MFC-ODBC-Consumers](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) zum Erstellen von View-Klasse und der zugehörigen Recordset-Klasse in Verbindung.  
  
 Der Datensatzansicht und dessen Recordset werden zerstört, wenn Sie das Dokument schließen. Weitere Informationen zu Datensatzansichten finden Sie unter [Datensatzansichten](../../data/record-views-mfc-data-access.md). Weitere Informationen über RFX finden Sie unter [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
## <a name="see-also"></a>Siehe auch  
 [ODBC und MFC](../../data/odbc/odbc-and-mfc.md)