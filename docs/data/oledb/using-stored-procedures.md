---
title: Verwenden von gespeicherten Prozeduren | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2a79ca28b3ae509ef5e493a23222ac76ad2352c9
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
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