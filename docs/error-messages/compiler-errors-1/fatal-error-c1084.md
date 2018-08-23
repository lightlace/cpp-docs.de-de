---
title: Schwerwiegender Fehler C1084 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1084
dev_langs:
- C++
helpviewer_keywords:
- C1084
ms.assetid: b2f273ef-3a14-4d5f-8ce0-7a11a0388fe6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: df584fd95921594562cf4c1fb912986343b30c4c
ms.sourcegitcommit: b92ca0b74f0b00372709e81333885750ba91f90e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/16/2018
ms.locfileid: "42541272"
---
# <a name="fatal-error-c1084"></a>Schwerwiegender Fehler C1084
Lesen der Dateityp-Datei 'Datei' nicht möglich: Meldung  
  
 Dieser Fehler ist im Allgemeinen das Ergebnis eines fehlgeschlagenen internen System-API-Aufrufs durch den Compiler. Die Meldung angezeigt, wenn dieser Fehler wird häufig durch eine generiert [_wcserror_s](../../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md) oder [FormatMessage](/windows/desktop/api/winbase/nf-winbase-formatmessage).  
  
 Mit den folgenden Schritten können Sie C1084 möglicherweise beheben:  
  
-   Stellen Sie sicher, dass die angegebene Datei existiert.  
  
-   Stellen Sie sicher, dass die geeigneten Berechtigungen festgelegt sind, um auf die angegebene Datei zuzugreifen.  
  
-   Stellen Sie sicher, die Befehlszeilensyntax die unter beschriebenen Regeln entspricht [Compiler Command-Line Syntax](../../build/reference/compiler-command-line-syntax.md).  
  
-   Stellen Sie sicher, dass die Umgebungsvariablen sicher **TMP** und **TEMP** sind ordnungsgemäß Satz als auch die entsprechenden Berechtigungen, um den Zugriff auf die Verzeichnisse diese Umgebungsvariablen beziehen. Außerdem stellen Sie sicher, dass die Laufwerke, die auf die verwiesen wird durch die **TMP** und **TEMP** Umgebungsvariablen enthalten eine ausreichende Menge des freien Speicherplatzes.  
  
-   Wenn die Meldung „Ungültige Dateinummer“ enthält, wurde die angegebene Datei möglicherweise im Vordergrund geschlossen, während sie im Hintergrund kompiliert wurde.  
  
 Führen Sie nach der Durchführung der obigen Diagnose einen bereinigten Build aus.