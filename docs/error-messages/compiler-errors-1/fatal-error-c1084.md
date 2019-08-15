---
title: Schwerwiegender Fehler C1084
ms.date: 11/04/2016
f1_keywords:
- C1084
helpviewer_keywords:
- C1084
ms.assetid: b2f273ef-3a14-4d5f-8ce0-7a11a0388fe6
ms.openlocfilehash: b0c8e6a8f8321dccdfd7cee128a4cf06cebda991
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69501136"
---
# <a name="fatal-error-c1084"></a>Schwerwiegender Fehler C1084

Lesen der Dateityp-Datei 'Datei' nicht möglich: Meldung

Dieser Fehler ist im Allgemeinen das Ergebnis eines fehlgeschlagenen internen System-API-Aufrufs durch den Compiler. Die Meldung, die angezeigt wird, wenn dieser Fehler auftritt, wird häufig durch [_wcserror_s](../../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md) oder [FormatMessage](/windows/win32/api/winbase/nf-winbase-formatmessage)generiert.

Mit den folgenden Schritten können Sie C1084 möglicherweise beheben:

- Stellen Sie sicher, dass die angegebene Datei existiert.

- Stellen Sie sicher, dass die geeigneten Berechtigungen festgelegt sind, um auf die angegebene Datei zuzugreifen.

- Stellen Sie sicher, dass die Befehlszeilen Syntax den in der [compilerbefehlszeilensyntax](../../build/reference/compiler-command-line-syntax.md)beschriebenen Regeln entspricht.

- Stellen Sie sicher, dass die Umgebungsvariablen " **tmp** " und " **Temp** " ordnungsgemäß festgelegt sind, sowie die entsprechenden Berechtigungen, um auf die Verzeichnisse zuzugreifen, auf die diese Umgebungsvariablen verweisen. Stellen Sie außerdem sicher, dass die Laufwerke, auf die die Umgebungsvariablen " **tmp** " und " **Temp** " verweisen, ausreichend freien Speicherplatz enthalten.

- Wenn die Meldung „Ungültige Dateinummer“ enthält, wurde die angegebene Datei möglicherweise im Vordergrund geschlossen, während sie im Hintergrund kompiliert wurde.

Führen Sie nach der Durchführung der obigen Diagnose einen bereinigten Build aus.