---
title: 'TN047: Abschwächen der Transaktionsanforderungen | Microsoft-Dokumentation'
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
ms.openlocfilehash: 96f3116f503ffa0ffc461ea2c1a0bdaf8947a0be
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46427016"
---
# <a name="tn047-relaxing-database-transaction-requirements"></a>TN047: Abschwächen der Anforderungen für eine Datenbanktransaktion

Diese technische Hinweise, die die Transaktion an die MFC-ODBC-Datenbankklassen erläutert, ist mittlerweile veraltet. Vor MFC 4.2, die Datenbankklassen erforderlich sind, dass Cursor bei Recordsets nach beibehalten werden eine **CommitTrans** oder **Rollback** Vorgang. Wenn die ODBC-Treiber und das DBMS diese Ebene der Beibehaltung der Cursor nicht unterstützt, die Datenbankklassen nicht Transaktionen aktivieren.

Ab MFC 4.2, haben die Beschränkung der Beibehaltung der Cursor erfordern die Datenbankklassen gelockert. Transaktionen aktiviert werden, wenn der Treiber unterstützt. Allerdings müssen Sie derzeit die Auswirkungen Überprüfen einer **CommitTrans** oder **Rollback** Vorgang auf dem geöffneten Recordsets. Die Memberfunktionen [GetCursorCommitBehavior](../mfc/reference/cdatabase-class.md#getcursorcommitbehavior) und [Rollback](../mfc/reference/cdatabase-class.md#getcursorrollbackbehavior) für Weitere Informationen.

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

