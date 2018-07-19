---
title: 'TN047: Abschwächen der Anforderungen für die Datenbank-Transaktionen eine | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.data
dev_langs:
- C++
helpviewer_keywords:
- TN047
ms.assetid: f93c51cf-a8c0-43d0-aa47-7bcb8333d693
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: be5870efacb61d5c0bb74f85427c41f787d2edd6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33380932"
---
# <a name="tn047-relaxing-database-transaction-requirements"></a>TN047: Abschwächen der Anforderungen für eine Datenbanktransaktion
Dieser Hinweis an den technischen, die die Anforderungen für Transaktionen in den MFC-ODBC-Datenbankklassen erläutert wird, ist mittlerweile veraltet. Bevor MFC-4.2 Datenbankklassen erforderlich, dass Cursor bei Recordsets nach beibehalten werden eine **CommitTrans** oder **Rollback** Vorgang. Wenn die ODBC-Treiber und DBMS dieses Maß an Beibehaltung der Cursor nicht unterstützt, haben die Datenbankklassen Transaktionen nicht aktiviert.  
  
 Ab MFC 4.2, haben die Beschränkung der Beibehaltung der Cursor erfordern die Datenbankklassen gelockert. Transaktionen werden aktiviert, wenn der Treiber unterstützt. Allerdings müssen Sie jetzt die Auswirkung Überprüfen einer **CommitTrans** oder **Rollback** Vorgang auf geöffneten Recordsets. Die Memberfunktionen [GetCursorCommitBehavior](../mfc/reference/cdatabase-class.md#getcursorcommitbehavior) und [Rollback](../mfc/reference/cdatabase-class.md#getcursorrollbackbehavior) für Weitere Informationen.  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

