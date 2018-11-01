---
title: ODBC und die Datenbankklassen
ms.date: 11/04/2016
helpviewer_keywords:
- database classes [C++], ODBC
- ODBC API functions [C++]
- ODBC classes [C++], MFC database classes
- MFC [C++], ODBC and
ms.assetid: b166f82d-6f85-4556-aac8-fb851235d22c
ms.openlocfilehash: 709608098a0c979cd7816ae4f8012372099ef52d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50575603"
---
# <a name="odbc-and-the-database-classes"></a>ODBC und die Datenbankklassen

Die MFC-ODBC-Datenbankklassen kapseln, die Sie normalerweise Sie selbst im Member-Funktionen des machen würden ODBC-API-Funktionsaufrufe der [CDatabase](../../mfc/reference/cdatabase-class.md) und [CRecordset](../../mfc/reference/crecordset-class.md) Klassen. Beispielsweise werden die komplexe Abfolgen von ODBC-Aufruf, der Bindung an zurückgegebenen Datensätzen Speicherorte, Behandeln von Fehlerzuständen und andere Vorgänge für Sie von den Datenbankklassen verwaltet. Daher verwenden Sie eine wesentlich einfachere Klassenschnittstelle, um Datensätze mit einem Recordset-Objekt zu ändern.

> [!NOTE]
>  Auf ODBC-Datenquellen können Sie über die MFC-ODBC-Klassen zugreifen, wie in diesem Thema beschrieben, oder über die MFC-Datenzugriffsobjekt-Klassen (DAO-Klassen).

Obwohl die Datenbankklassen ODBC-Funktionen kapseln, bieten sie eine einfache Zuordnung der ODBC-API-Funktionen nicht. Die Datenbankklassen bieten eine höhere Abstraktionsebene, die modelliert werden, nachdem Datenzugriffs-Objekten in Microsoft Access und Microsoft Visual Basic gefunden. Weitere Informationen finden Sie unter [ODBC und MFC](../../data/odbc/odbc-and-mfc.md).

## <a name="see-also"></a>Siehe auch

[Grundlagen zu ODBC](../../data/odbc/odbc-basics.md)