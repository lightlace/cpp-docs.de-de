---
title: Schwerwiegender Fehler C1084 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1084
dev_langs:
- C++
helpviewer_keywords:
- C1084
ms.assetid: b2f273ef-3a14-4d5f-8ce0-7a11a0388fe6
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: caf1e64e91871087c9e47860a41c2824a811295a
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

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
