---
title: Befehlshandler für das Scrollen von Datensätzen (MFC-Datenzugriff)
ms.date: 11/04/2016
helpviewer_keywords:
- record views [C++], scrolling
- record scrolling [C++]
- scrolling records
ms.assetid: f8b13477-2a37-459e-a30c-806fb78165ac
ms.openlocfilehash: 66944221910dbd23d78a78fc951030efbee86bd0
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59038515"
---
# <a name="command-handlers-for-record-scrolling--mfc-data-access"></a>Befehlshandler für das Scrollen von Datensätzen (MFC-Datenzugriff)

Die [CRecordView](../mfc/reference/crecordview-class.md) -Klasse bietet die Standardbefehlsbehandlung für die folgenden Standardbefehle:

- ID_RECORD_MOVE_FIRST

- ID_RECORD_MOVE_LAST

- ID_RECORD_MOVE_NEXT

- ID_RECORD_MOVE_PREV

Die `OnMove` Member-Funktion bietet die Standardbefehlsbehandlung für alle vier Befehle, die von Datensatz zu Datensatz verschoben. Nachdem diese Befehle ausgegeben wurden, lädt RFX (oder DFX) den neuen Datensatz in die Recordset-Felder, und DDX verschiebt die Werte in die Steuerelemente des Datensatzformulars. Weitere Informationen über RFX finden Sie unter [Datensatzfeldaustausch (RFX)](../data/odbc/record-field-exchange-rfx.md).

> [!NOTE]
>  Verwenden Sie diese Standardbefehls-IDs für alle Benutzeroberflächenobjekte, die den standardmäßigen Navigationsbefehlen des Datensatzes zugeordnet sind.

## <a name="see-also"></a>Siehe auch

[Navigationsunterstützung in einer Datensatzansicht](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)