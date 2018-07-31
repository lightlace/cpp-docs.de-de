---
title: Verwenden von gespeicherten Prozeduren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: fe62aff7e8828dcb17c04fc3e05eedc9eefe9d16
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337280"
---
# <a name="using-stored-procedures"></a>Verwenden von gespeicherten Prozeduren
Eine gespeicherte Prozedur ist eine in einer Datenbank gespeichertes, ausführbares Objekt. Aufrufen einer gespeicherten Prozedur entspricht einen SQL-Befehl aufrufen. Verwenden von gespeicherten Prozeduren in der Datenquelle (anstelle von ausführen oder das Vorbereiten einer Anweisung in der Clientanwendung) bieten mehrere Vorteile, u.a. höhere Leistung, geringere Aufwand, und verbesserte Konsistenz und Genauigkeit.  
  
 Eine gespeicherte Prozedur kann eine beliebige Anzahl von (einschließlich NULL) haben Eingabe- oder Ausgabeparameter und einen Rückgabewert übergeben können. Sie können entweder Parameterwerte fest programmieren, wie bestimmte Daten Werte, oder eine parametermarkierung verwenden (ein Fragezeichen ersetzt ein "?").  
  
> [!NOTE]
>  CLR von SQL Server gespeicherte Prozeduren, die mit Visual C++ erstellten müssen kompiliert werden, mit der `/clr:safe` -Compileroption.  
  
 Der OLE DB-Anbieter für SQL Server (SQLOLEDB) unterstützt die folgenden Mechanismen, die gespeicherten Prozeduren verwenden, um Daten zurückzugeben:  
  
-   Jede SELECT-Anweisung in der Prozedur generiert ein Resultset.  
  
-   Die Prozedur kann Daten über Ausgabeparameter zurückgeben.  
  
-   Die Prozedur kann einen ganzzahligen Rückgabecode besitzen.  
  
> [!NOTE]
>  Sie können gespeicherte Prozeduren mit dem OLE DB-Anbieter für Jet verwenden, da es sich bei diesen Anbieter gespeicherte Prozeduren nicht unterstützt; nur Konstanten sind in die Abfragezeichenfolgen zulässig.  
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit OLE DB-Consumervorlagen](../../data/oledb/working-with-ole-db-consumer-templates.md)