---
title: "Schwerwiegender Fehler C1084 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1084"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1084"
ms.assetid: b2f273ef-3a14-4d5f-8ce0-7a11a0388fe6
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Schwerwiegender Fehler C1084
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lesen der Dateityp\-Datei 'Datei' nicht möglich: Meldung  
  
 Dieser Fehler ist im Allgemeinen das Ergebnis eines fehlgeschlagenen internen System\-API\-Aufrufs durch den Compiler.  Die Meldung, die bei Auftreten dieses Fehlers angezeigt wird, wird oft entweder von [\_wcserror\_s](../../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md) oder von [FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351.aspx) generiert.  
  
 Mit den folgenden Schritten können Sie C1084 möglicherweise beheben:  
  
-   Stellen Sie sicher, dass die angegebene Datei existiert.  
  
-   Stellen Sie sicher, dass die geeigneten Berechtigungen festgelegt sind, um auf die angegebene Datei zuzugreifen.  
  
-   Stellen Sie sicher, dass die Befehlszeilensyntax die unter [Syntax für die Compilerbefehlszeile](../../build/reference/compiler-command-line-syntax.md) aufgeführten Regeln einhält.  
  
-   Stellen Sie sicher, dass die Umgebungsvariablen **TMP** und **TEMP** sowie die geeigneten Berechtigungen für den Zugriff auf die Verzeichnisse, auf die sich diese Umgebungsvariablen beziehen, ordnungsgemäß festgelegt sind.  Stellen Sie außerdem sicher, dass die von den Umgebungsvariablen **TMP** und **TEMP** referenzierten Laufwerke eine angemessene Menge freien Speicherplatz enthalten.  
  
-   Wenn die Meldung „Ungültige Dateinummer“ enthält, wurde die angegebene Datei möglicherweise im Vordergrund geschlossen, während sie im Hintergrund kompiliert wurde.  
  
 Führen Sie nach der Durchführung der obigen Diagnose einen bereinigten Build aus.