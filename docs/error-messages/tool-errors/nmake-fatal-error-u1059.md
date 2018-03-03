---
title: 'NMAKE: Schwerwiegender Fehler U1059 | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- U1059
dev_langs:
- C++
helpviewer_keywords:
- U1059
ms.assetid: b21d9198-9c63-40d0-b589-80e17294ce24
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fb9ba98b0f82c158e4e11859e85af72efdbbc244
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1059"></a>NMAKE: Schwerwiegender Fehler U1059
Syntaxfehler: '}' fehlt in der abhängigen  
  
 Ein Suchpfad für eine abhängige Datei wurde falsch angegeben. Entweder ist ein Leerzeichen im Pfad oder die schließende geschweifte Klammer (**}**) wurde ausgelassen.  
  
 Die Syntax für eine Verzeichnisangabe für eine abhängige Datei  
  
 **{**   
 ***Verzeichnisse* } abhängige**  
  
 wobei `directories` gibt einen oder mehrere Pfade, jeweils durch ein Semikolon getrennt (**;**). Es sind keine Leerzeichen zulässig.  
  
 Wenn einem Suchpfad ganz oder teilweise von einem Makro ersetzt wird, stellen Sie sicher, dass keine Leerzeichen in der makroerweiterung vorhanden sind.