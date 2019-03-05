---
title: 'TN047: Abschwächen der Anforderungen für die Transaktion'
ms.date: 11/04/2016
f1_keywords:
- vc.data
helpviewer_keywords:
- TN047
ms.assetid: f93c51cf-a8c0-43d0-aa47-7bcb8333d693
ms.openlocfilehash: 968420658a90c983d8e6c3eaf1e0c61603fc5441
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57276805"
---
# <a name="tn047-relaxing-database-transaction-requirements"></a>TN047: Abschwächen der Anforderungen für die Transaktion

Diese technische Hinweise, die die Transaktion an die MFC-ODBC-Datenbankklassen erläutert, ist mittlerweile veraltet. Vor MFC 4.2, die Datenbankklassen erforderlich sind, dass Cursor bei Recordsets nach beibehalten werden eine **CommitTrans** oder **Rollback** Vorgang. Wenn die ODBC-Treiber und das DBMS diese Ebene der Beibehaltung der Cursor nicht unterstützt, die Datenbankklassen nicht Transaktionen aktivieren.

Ab MFC 4.2, haben die Beschränkung der Beibehaltung der Cursor erfordern die Datenbankklassen gelockert. Transaktionen aktiviert werden, wenn der Treiber unterstützt. Allerdings müssen Sie derzeit die Auswirkungen Überprüfen einer **CommitTrans** oder **Rollback** Vorgang auf dem geöffneten Recordsets. Die Memberfunktionen [GetCursorCommitBehavior](../mfc/reference/cdatabase-class.md#getcursorcommitbehavior) und [Rollback](../mfc/reference/cdatabase-class.md#getcursorrollbackbehavior) für Weitere Informationen.

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)
