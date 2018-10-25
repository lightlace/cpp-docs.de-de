---
title: Erstellen eines einfachen schreibgeschützten Anbieters | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, creating
- OLE DB provider templates, creating providers
ms.assetid: ade8ccdd-9ea4-4e46-a964-18460c2a2401
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b32517e8254f383e624c5262f3a806e66ed28824
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50056255"
---
# <a name="creating-a-simple-read-only-provider"></a>Erstellen eines einfachen schreibgeschützten Anbieters

Wenn Sie einen OLE DB-Anbieter, die mit dem ATL-Projektassistenten und ATL-OLE DB-Anbieter-Assistenten erstellt haben, können Sie weitere Funktionen hinzufügen, die Sie unterstützen möchten. Starten Sie das Entwerfen von Ihrem Anbieter anhand der Art von Daten, die Sie an den Consumer und unter welchen Bedingungen gesendet werden. Es ist besonders wichtig, um festzustellen, ob die Befehle, Transaktionen und andere optionale Objekte unterstützt werden müssen. Ein guter Entwurf voraus wird die Implementierung und Testen beschleunigen.

Im Beispiel wird in zwei Teile untergliedert:

- Der erste Teil zeigt wie [erstellen ein einfaches schreibgeschützten Anbieters](../../data/oledb/implementing-the-simple-read-only-provider.md) , liest es sich um ein Paar von Zeichenfolgen.

- Der zweite Teil zeigt wie [Erweitern des einfachen schreibgeschützten Anbieters](../../data/oledb/enhancing-the-simple-read-only-provider.md) durch Hinzufügen der `IRowsetLocate` Schnittstelle.

## <a name="see-also"></a>Siehe auch

[Erstellen eines OLE DB-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)