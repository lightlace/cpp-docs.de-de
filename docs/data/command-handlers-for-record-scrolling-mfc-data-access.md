---
title: Befehls-Handler für (MFC-Datenzugriff) Scrollen von Datensätzen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- record views [C++], scrolling
- record scrolling [C++]
- scrolling records
ms.assetid: f8b13477-2a37-459e-a30c-806fb78165ac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b51a6e9c9cf9516ed86066f712a17fea69c3cb50
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46112238"
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