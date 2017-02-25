---
title: "Projektbuildfehler PRJ0025 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0025"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0025"
ms.assetid: 57725c78-bc63-44f3-9667-2969b2d7c41d
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Projektbuildfehler PRJ0025
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Batchdatei "Datei" enthält Unicodeinhalt, der nicht in die ANSI\-Codepage des Benutzers übersetzt werden konnte.  
  
 ***UNICODE\-Inhalt der Datei***  
  
 Das Projektsystem hat Unicodeinhalt in einer benutzerdefinierten Buildregel oder einem Buildereignis gefunden, der nicht ordnungsgemäß in die aktuelle ANSI\-Codepage des Benutzers übersetzt werden kann.  
  
 Die Lösung dieses Problems besteht darin, dass Sie den Inhalt der Buildregel oder des Buildereignisses unter Verwendung von ANSI aktualisieren oder die Codepage auf dem Computer installieren und als Systemstandard festlegen.  
  
 Weitere Informationen zu benutzerdefinierten Buildschritten und Buildereignissen finden Sie unter [Benutzerdefinierte Buildschritte und Buildereignisse](../../ide/understanding-custom-build-steps-and-build-events.md).