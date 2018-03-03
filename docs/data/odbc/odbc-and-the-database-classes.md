---
title: ODBC und die Datenbankklassen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- database classes [C++], ODBC
- ODBC API functions [C++]
- ODBC classes [C++], MFC database classes
- MFC [C++], ODBC and
ms.assetid: b166f82d-6f85-4556-aac8-fb851235d22c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e3041a4fc027a8786fb62db7df6eaf486633ce97
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="odbc-and-the-database-classes"></a>ODBC und die Datenbankklassen
Die MFC-ODBC-Datenbankklassen zu kapseln, die Sie normalerweise selbst im Member-Funktionen von machen würden ODBC-API-Funktionsaufrufe der [CDatabase](../../mfc/reference/cdatabase-class.md) und [CRecordset](../../mfc/reference/crecordset-class.md) Klassen. Beispielsweise sind die komplexen ODBC Call-Sequenzen, die Bindung der zurückgegebenen Datensätze auf Speicherorte, Behandeln von Fehlerzuständen und andere Vorgänge für Sie von den Datenbankklassen verwaltet. Daher verwenden Sie eine wesentlich einfachere Klassenschnittstelle zum Bearbeiten von Datensätzen über einem Recordset-Objekt.  
  
> [!NOTE]
>  Auf ODBC-Datenquellen können Sie über die MFC-ODBC-Klassen zugreifen, wie in diesem Thema beschrieben, oder über die MFC-Datenzugriffsobjekt-Klassen (DAO-Klassen).  
  
 Obwohl die Datenbankklassen ODBC-Funktionalität kapseln, bieten keine 1: 1-Zuordnung von ODBC-API-Funktionen. Die Datenbankklassen bieten ein höheres Maß an Abstraktion, die modelliert werden, nachdem der Datenzugriffs-Objekte in Microsoft Access und Microsoft Visual Basic gefunden. Weitere Informationen finden Sie unter [ODBC und MFC](../../data/odbc/odbc-and-mfc.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlagen zu ODBC](../../data/odbc/odbc-basics.md)