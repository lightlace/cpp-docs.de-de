---
title: Schwerwiegender Fehler C1902 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1902
dev_langs:
- C++
helpviewer_keywords:
- C1902
ms.assetid: 2dc066cc-fcb1-4725-8bcb-9f44dd0905b7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b23507b6531f9ee4e5ce5efd5b60a1977206635c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33228198"
---
# <a name="fatal-error-c1902"></a>Schwerwiegender Fehler C1902
Fehlende Übereinstimmung Programm Datenbank-Manager; Bitte überprüfen Sie die installation  
  
Erstellt eine Programmdatenbankdatei (.pdb) wurde mit einer neueren Version von Mspdb*XXX*DLL demjenigen, der Compiler auf Ihrem System gefunden. Dieser Fehler gibt normalerweise an, dass mspdbsrv.exe oder mspdbcore.dll fehlen oder andere Versionen als Mspdb*XXX*DLL. (Die *XXX* Platzhalter in der Mspdb*XXX*.dll-Datei ändert sich mit jeder Produktversion. Beispielsweise wird in Visual Studio 2015 ist der Dateiname mspdb140.dll.)  
  
Stellen Sie sicher übereinstimmende Versionen von mspdbsrv.exe, mspdbcore.dll und Mspdb*XXX*DLL-Datei auf Ihrem System installiert sind. Stellen Sie sicher, dass nicht übereinstimmende Versionen nicht in das Verzeichnis kopiert wurden, die der Compiler und Link-Tools für die Zielplattform enthält. Angenommen, Sie können kopiert haben die Dateien, damit der Compiler oder Link-Tool über die Eingabeaufforderung festlegen, ohne aufgerufen werden konnte die **Pfad** Umgebungsvariable entsprechend.