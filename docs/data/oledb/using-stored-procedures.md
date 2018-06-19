---
title: Verwenden von gespeicherten Prozeduren | Microsoft Docs
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
ms.openlocfilehash: e5b49daa44fc8c88316134915945ad7ee01bb81a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33112237"
---
# <a name="using-stored-procedures"></a>Verwenden von gespeicherten Prozeduren
Eine gespeicherte Prozedur ist eine in einer Datenbank gespeichertes, ausführbares Objekt. Aufrufen einer gespeicherten Prozedur ist ähnlich wie einen SQL-Befehl aufrufen. Verwenden von gespeicherten Prozeduren für die Datenquelle (anstelle der Ausführung, oder Vorbereiten einer Anweisung in der Clientanwendung) bieten mehrere Vorteile, einschließlich höhere Leistung, weniger netzwerkmehraufwand, verbesserte Konsistenz und Genauigkeit.  
  
 Eine gespeicherte Prozedur kann eine beliebige Anzahl von (einschließlich 0 (null)) haben Eingabe- oder Ausgabeparameter und einen Rückgabewert übergeben können. Sie können entweder hartcodieren Parameterwerte, bei der bestimmte Daten Werte oder eine parametermarkierung verwendet (ein Fragezeichen ersetzt ein "?").  
  
> [!NOTE]
>  CLR-SQL-Server mithilfe von Visual C++ erstellte gespeicherte Prozeduren müssen kompiliert werden, mit der **/CLR: safe** -Compileroption.  
  
 Der OLE DB-Anbieter für SQL Server (SQLOLEDB) unterstützt die folgenden Mechanismen, die gespeicherten Prozeduren verwenden, um Daten zurückzugeben:  
  
-   Jede SELECT-Anweisung in der Prozedur generiert ein Resultset.  
  
-   Die Prozedur kann Daten über Ausgabeparameter zurückgeben.  
  
-   Die Prozedur kann einen ganzzahligen Rückgabecode besitzen.  
  
> [!NOTE]
>  Sie können gespeicherte Prozeduren mit dem OLE DB-Anbieter für Jet verwenden, da dieser Anbieter keine gespeicherten Prozeduren unterstützt; nur Konstanten sind in Abfragezeichenfolgen zulässig.  
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit OLE DB-Consumervorlagen](../../data/oledb/working-with-ole-db-consumer-templates.md)