---
title: Weitervertrieb von ODBC-Komponenten an Ihre Kunden | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ODBC components, redistributing
- ODBC, distributing components
- components [C++], distributing
- ODBC Administrator
- components [C++]
- components [C++], redistributing
ms.assetid: 17b065b4-a307-4b89-99ac-d05831cfab87
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: aad9f1dbd4542ad763e7303d9a750f1856208025
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="redistributing-odbc-components-to-your-customers"></a>Weitervertrieb von ODBC-Komponenten an Kunden
Wenn Sie die Funktionalität der ODBC-Administrator Programme in Ihre Anwendung integrieren, müssen Sie auch für Ihre Benutzer die Dateien verteilen, auf denen diese Programme ausgeführt. Diese ODBC-Dateien befinden sich im Verzeichnis \OS\System der Visual C++-CD. Die Datei Redistrb.wri und den Lizenzvertrag im selben Verzeichnis enthalten eine Liste der ODBC-Dateien, die Sie verteilen können.  
  
 Die Dokumentation für ODBC-Treiber, die Sie versenden möchten. Sie müssen, um zu bestimmen, welche DLLs und andere Dateien senden. Lesen Sie auch [Weitervertrieb von ODBC-Komponenten an Ihre Kunden](../../data/odbc/redistributing-odbc-components-to-your-customers.md), die erklärt, wie ODBC-Komponenten neu zu verteilen.  
  
 Darüber hinaus müssen Sie eine andere Datei in den meisten Fällen enthalten. Die Datei Odbccr32.dll ist die ODBC-Cursorbibliothek. Diese Bibliothek kann Level 1-Treibern Dienstvorlagen Bildlauf vorwärts und rückwärts. Darüber hinaus bietet die Möglichkeit der Unterstützung von Momentaufnahmen. Weitere Informationen zu den ODBC-Cursorbibliothek, finden Sie unter [ODBC: die ODBC-Cursorbibliothek](../../data/odbc/odbc-the-odbc-cursor-library.md).  
  
 Die folgenden Themen enthalten weitere Informationen zur Verwendung von ODBC mit den Datenbankklassen:  
  
-   [ODBC: Die ODBC-Cursorbibliothek](../../data/odbc/odbc-the-odbc-cursor-library.md)  
  
-   [ODBC: Konfigurieren einer ODBC-Datenquelle](../../data/odbc/odbc-configuring-an-odbc-data-source.md)  
  
-   [ODBC: Direktes Aufrufen von ODBC-API-Funktionen](../../data/odbc/odbc-calling-odbc-api-functions-directly.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlagen zu ODBC](../../data/odbc/odbc-basics.md)   
 [ODBC-Administrator](../../data/odbc/odbc-administrator.md)