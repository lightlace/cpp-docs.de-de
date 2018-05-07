---
title: 'NMAKE: Schwerwiegender Fehler U1059 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1059
dev_langs:
- C++
helpviewer_keywords:
- U1059
ms.assetid: b21d9198-9c63-40d0-b589-80e17294ce24
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6eb038befdb7c587c6fe2a734003abba585c3e2a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="nmake-fatal-error-u1059"></a>NMAKE: Schwerwiegender Fehler U1059
Syntaxfehler: '}' fehlt in der abhängigen  
  
 Ein Suchpfad für eine abhängige Datei wurde falsch angegeben. Entweder ist ein Leerzeichen im Pfad oder die schließende geschweifte Klammer (**}**) wurde ausgelassen.  
  
 Die Syntax für eine Verzeichnisangabe für eine abhängige Datei  
  
 **{**   
 ***Verzeichnisse* } abhängige**  
  
 wobei `directories` gibt einen oder mehrere Pfade, jeweils durch ein Semikolon getrennt (**;**). Es sind keine Leerzeichen zulässig.  
  
 Wenn einem Suchpfad ganz oder teilweise von einem Makro ersetzt wird, stellen Sie sicher, dass keine Leerzeichen in der makroerweiterung vorhanden sind.