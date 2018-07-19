---
title: Schwerwiegender Fehler C1084 | Microsoft Docs
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
ms.openlocfilehash: a7266a2158c3e6ccd02ea82de22c6f90a8b6363d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33229388"
---
# <a name="fatal-error-c1084"></a>Schwerwiegender Fehler C1084
Lesen der Dateityp-Datei 'Datei' nicht möglich: Meldung  
  
 Dieser Fehler ist im Allgemeinen das Ergebnis eines fehlgeschlagenen internen System-API-Aufrufs durch den Compiler. Die Meldung angezeigt, wenn dieser Fehler wird häufig generiert, entweder durch [_wcserror_s](../../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md) oder [FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351.aspx).  
  
 Mit den folgenden Schritten können Sie C1084 möglicherweise beheben:  
  
-   Stellen Sie sicher, dass die angegebene Datei existiert.  
  
-   Stellen Sie sicher, dass die geeigneten Berechtigungen festgelegt sind, um auf die angegebene Datei zuzugreifen.  
  
-   Stellen Sie sicher, die unter beschriebenen Regeln entspricht die Befehlszeilensyntax [Compiler Befehlszeilensyntax](../../build/reference/compiler-command-line-syntax.md).  
  
-   Gewährleisten Sie sicher, dass die Umgebungsvariablen **TMP** und **TEMP** sind ordnungsgemäß festlegen sowie die entsprechenden Berechtigungen, um auf die Verzeichnisse zugreifen, diese Umgebungsvariablen beziehen. Zudem sicherstellen, dass die Laufwerke, auf die verwiesen wird durch die **TMP** und **TEMP** Umgebungsvariablen enthalten eine ausreichende Menge des freien Speicherplatzes.  
  
-   Wenn die Meldung „Ungültige Dateinummer“ enthält, wurde die angegebene Datei möglicherweise im Vordergrund geschlossen, während sie im Hintergrund kompiliert wurde.  
  
 Führen Sie nach der Durchführung der obigen Diagnose einen bereinigten Build aus.