---
title: Schwerwiegender Fehler C1902 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1902
dev_langs:
- C++
helpviewer_keywords:
- C1902
ms.assetid: 2dc066cc-fcb1-4725-8bcb-9f44dd0905b7
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 89354565f67c8704eee8c8b5f9dcb94523800c63
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="fatal-error-c1902"></a>Schwerwiegender Fehler C1902
Fehlende Übereinstimmung Programm Datenbank-Manager; Bitte überprüfen Sie die installation  
  
Erstellt eine Programmdatenbankdatei (.pdb) wurde mit einer neueren Version von Mspdb*XXX*DLL demjenigen, der Compiler auf Ihrem System gefunden. Dieser Fehler gibt normalerweise an, dass mspdbsrv.exe oder mspdbcore.dll fehlen oder andere Versionen als Mspdb*XXX*DLL. (Die *XXX* Platzhalter in der Mspdb*XXX*.dll-Datei ändert sich mit jeder Produktversion. Beispielsweise wird in Visual Studio 2015 ist der Dateiname mspdb140.dll.)  
  
Stellen Sie sicher übereinstimmende Versionen von mspdbsrv.exe, mspdbcore.dll und Mspdb*XXX*DLL-Datei auf Ihrem System installiert sind. Stellen Sie sicher, dass nicht übereinstimmende Versionen nicht in das Verzeichnis kopiert wurden, die der Compiler und Link-Tools für die Zielplattform enthält. Angenommen, Sie können kopiert haben die Dateien, damit der Compiler oder Link-Tool über die Eingabeaufforderung festlegen, ohne aufgerufen werden konnte die **Pfad** Umgebungsvariable entsprechend.
