---
title: Codepages | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.international
dev_langs:
- C++
helpviewer_keywords:
- character sets [C++], code pages
- ANSI [C++], code pages
- system-default code page
- multibyte code pages [C++]
- localization [C++], code pages
- code pages [C++], types of
- locale code pages [C++]
ms.assetid: 4a26fc42-185a-4add-98bf-a7b314ae6186
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6eafdf3a140dd8a5976cf2fe8554b3b076111b74
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50060506"
---
# <a name="code-pages"></a>Codepages

Eine *Codepage* ist ein Zeichensatz, der Zahlen, Interpunktionszeichen und andere Glyphen enthalten kann. Von unterschiedlichen Sprachen und Gebietsschemas werden möglicherweise unterschiedliche Codepages verwendet. Die ANSI-Codepage 1252 wird z.B. für Englisch und die meisten europäischen Sprachen verwendet, während die OEM-Codepage 932 für das japanische Kanji eingesetzt wird.

Eine Codepage kann in einer Tabelle als Zuordnung von Zeichen zu Einzelbyte- oder Multibyte-Werten dargestellt werden. Viele Codepages verwenden den ASCII-Zeichensatz für Zeichen im Bereich von 0x00 bis 0x7F.

Die Microsoft-Laufzeitbibliothek verwendet die folgenden Typen von Codepages:

- Standard-ANSI-Codepage des Systems. In der Standardeinstellung legt das Laufzeitsystem beim Start die Multibyte-Codepage automatisch auf die Standard-ANSI-Codepage des Systems fest, die aus dem Betriebssystem abgerufen wird. Der Aufruf

    ```C
    setlocale ( LC_ALL, "" );
    ```

   legt auch das Gebietsschema auf die Standard-ANSI-Codepage des Systems fest.

- Gebietsschema-Codepage. Das Verhalten einiger Laufzeitroutinen ist abhängig von der aktuellen Einstellung des Gebietsschemas, das die Gebietsschema-Codepage enthält. (Weitere Informationen finden Sie unter [Locale-Dependent Routines (Vom Gebietsschema abhängige Routinen)](../c-runtime-library/locale.md).) In der Standardeinstellung verwenden alle vom Gebietsschema abhängigen Routinen in der Microsoft-Laufzeitbibliothek die Codepage, die dem Gebietsschema „C“ entspricht. Zur Laufzeit können Sie die verwendete Gebietsschema-Codepage ändern oder abfragen, indem Sie [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) aufrufen.

- Multibyte-Codepage. Das Verhalten der meisten Multibytezeichenroutinen in der Laufzeitbibliothek hängt von der aktuellen Einstellung der Multibyte-Codepage ab. In der Standardeinstellung verwenden diese Routinen die Standard-ANSI-Codepage des Systems. Zur Laufzeit können Sie die Multibyte-Codepage mit [_getmbcp](../c-runtime-library/reference/getmbcp.md) oder [_setmbcp](../c-runtime-library/reference/setmbcp.md) abfragen bzw. ändern.

- Das Gebietsschema „C“ wird von ANSI so definiert, das es dem Gebietsschema entspricht, in dem C-Programme bisher ausgeführt wurden. Die Codepage für das Gebietsschema „C“ („C“-Codepage) entspricht dem ASCII-Zeichensatz. Zum Beispiel gibt **islower** im Gebietsschema „C“ nur für die Werte 0x61 bis 0x7A TRUE zurück. In einem anderen Gebietsschema kann **islower** sowohl für diese als auch für andere Werte TRUE zurückgeben, wenn es in diesem Gebietsschema so definiert wurde.

## <a name="see-also"></a>Siehe auch

[Internationalisierung](../c-runtime-library/internationalization.md)<br/>
[Universelle C-Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)<br/>