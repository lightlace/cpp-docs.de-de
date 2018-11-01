---
title: Weitervertrieb von ODBC-Komponenten an Kunden
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC components, redistributing
- ODBC, distributing components
- components [C++], distributing
- ODBC Administrator
- components [C++]
- components [C++], redistributing
ms.assetid: 17b065b4-a307-4b89-99ac-d05831cfab87
ms.openlocfilehash: cfbe6b2c440f84a4c470255bc964adf6c5145cf1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50676785"
---
# <a name="redistributing-odbc-components-to-your-customers"></a>Weitervertrieb von ODBC-Komponenten an Kunden

Wenn Sie die Funktionen der ODBC-Administrator-Programme in Ihrer Anwendung zu integrieren, müssen Sie auch für Ihre Benutzer die Dateien verteilen, die diese Programme ausgeführt werden. Diese ODBC-Dateien befinden sich in das Verzeichnis \OS\System der Visual C++-CD. Die Datei Redistrb.wri und den Lizenzvertrag im gleichen Verzeichnis enthalten eine Liste der ODBC-Dateien, die Sie erneut verteilen können.

Lesen Sie die Dokumentation für ODBC-Treiber, die Sie versenden möchten. Sie benötigen, um zu bestimmen, welche DLLs und andere Dateien senden. Lesen Sie auch [Weitervertrieb von ODBC-Komponenten für Ihre Kunden](../../data/odbc/redistributing-odbc-components-to-your-customers.md), die erklärt, wie ODBC-Komponenten neu zu verteilen.

Darüber hinaus müssen Sie eine andere Datei in den meisten Fällen enthalten. Die Datei Odbccr32.dll ist die ODBC-Cursorbibliothek. Diese Bibliothek kann auf Ebene 1-Treiber den Bildlauf vorwärts und rückwärts. Darüber hinaus die Möglichkeit, Momentaufnahmen zu unterstützen. Weitere Informationen zu den ODBC-Cursorbibliothek, finden Sie unter [ODBC: die ODBC-Cursorbibliothek](../../data/odbc/odbc-the-odbc-cursor-library.md).

Weitere Informationen zur Verwendung von ODBC mit den Datenbankklassen Sie in den folgenden Themen:

- [ODBC: Die ODBC-Cursorbibliothek](../../data/odbc/odbc-the-odbc-cursor-library.md)

- [ODBC: Konfigurieren einer ODBC-Datenquelle](../../data/odbc/odbc-configuring-an-odbc-data-source.md)

- [ODBC: Direktes Aufrufen von ODBC-API-Funktionen](../../data/odbc/odbc-calling-odbc-api-functions-directly.md)

## <a name="see-also"></a>Siehe auch

[Grundlagen zu ODBC](../../data/odbc/odbc-basics.md)<br/>
[ODBC-Administrator](../../data/odbc/odbc-administrator.md)