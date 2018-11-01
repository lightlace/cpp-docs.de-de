---
title: Verwenden von gespeicherten Prozeduren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/24/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB, stored procedures
- stored procedures, Visual C++
- stored procedures, about stored procedures
- OLE DB provider templates, stored procedures
- stored procedures, OLE DB
ms.assetid: 90507e4c-eca2-46c9-ad8c-07e10dc1d41b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 062384713e0668965f9d04dc8f6907b05ac2bc89
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50076879"
---
# <a name="using-stored-procedures"></a>Verwenden von gespeicherten Prozeduren

Eine gespeicherte Prozedur ist eine in einer Datenbank gespeichertes, ausführbares Objekt. Aufrufen einer gespeicherten Prozedur entspricht einen SQL-Befehl aufrufen. Verwenden von gespeicherten Prozeduren in der Datenquelle (anstelle von ausführen oder das Vorbereiten einer Anweisung in der Clientanwendung) bieten mehrere Vorteile, u.a. höhere Leistung, geringere Aufwand, und verbesserte Konsistenz und Genauigkeit.

Eine gespeicherte Prozedur kann eine beliebige Anzahl von (einschließlich NULL) haben Eingabe- oder Ausgabeparameter und einen Rückgabewert übergeben können. Sie können entweder Parameterwerte fest programmieren, wie bestimmte Daten Werte, oder eine parametermarkierung verwenden (ein Fragezeichen ersetzt ein "?").

> [!NOTE]
>  CLR von SQL Server gespeicherte Prozeduren, die mit Visual C++ erstellten müssen kompiliert werden, mit der `/clr:safe` -Compileroption.

Der OLE DB-Anbieter für SQL Server (SQLOLEDB) unterstützt die folgenden Mechanismen, die gespeicherten Prozeduren verwenden, um Daten zurückzugeben:

- Jede **wählen** Anweisung in der Prozedur generiert ein Resultset.

- Die Prozedur kann Daten über Ausgabeparameter zurückgeben.

- Die Prozedur kann einen ganzzahligen Rückgabecode besitzen.

> [!NOTE]
> Sie können gespeicherte Prozeduren mit dem OLE DB-Anbieter für Jet verwenden, da es sich bei diesen Anbieter gespeicherte Prozeduren nicht unterstützt; nur Konstanten sind in die Abfragezeichenfolgen zulässig.

## <a name="see-also"></a>Siehe auch

[Arbeiten mit OLE DB-Consumervorlagen](../../data/oledb/working-with-ole-db-consumer-templates.md)